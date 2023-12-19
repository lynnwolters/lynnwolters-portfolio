<script>
import { onMount } from 'svelte';
import * as THREE from 'three';

let container;
let canvasEl;

let renderer, scene, camera, clock, material;
let pointer = new THREE.Vector2(0.5, 0.5);
let targetPointer = new THREE.Vector2(0.5, 0.5);

const params = {
    coloring: 0.2,
    speed: 0.1,
}

onMount(() => {
    initScene()
    window.addEventListener('resize', updateSceneSize)

    window.addEventListener('mousemove', (e) => {
    updateMousePosition(e.clientX, e.clientY)
    })

    window.addEventListener('touchmove', (e) => {
    updateMousePosition(e.targetTouches[0].pageX, e.targetTouches[0].pageY)
    })

    return () => {
    window.removeEventListener('resize', updateSceneSize)
    }
})

function updateMousePosition(eX, eY) {
    targetPointer.x = eX / window.innerWidth
    targetPointer.y = 1.0 - eY / window.innerHeight
}

function initScene() {
    container = document.querySelector('.container')
    canvasEl = document.querySelector('#canvas')

    renderer = new THREE.WebGLRenderer({
    alpha: true,
    canvas: canvasEl,
    })
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))

    scene = new THREE.Scene()
    camera = new THREE.OrthographicCamera(-0.5, 0.5, 0.5, -0.5, 0.1, 10)
    clock = new THREE.Clock()

    material = new THREE.ShaderMaterial({
    uniforms: {
        u_point: { type: 'v2', value: pointer },
        u_resolution: { type: 'v2', value: new THREE.Vector2(0, 0) },
        u_time: { type: 'f', value: 0 },
        u_ratio: { type: 'f', value: window.innerWidth / window.innerHeight },
        u_width: { type: 'f', value: window.innerWidth },

        u_strength: { type: 'f', value: params.strength },
        u_coloring: { type: 'f', value: params.coloring },
        u_speed: { type: 'f', value: params.speed },
    },
    vertexShader: vertexShaderSource,
    fragmentShader: fragmentShaderSource,
    transparent: true,
    })

    const planeGeometry = new THREE.PlaneGeometry(2, 2)
    scene.add(new THREE.Mesh(planeGeometry, material))

    updateSceneSize()
    render()
}

function render() {
    pointer.x += (targetPointer.x - pointer.x) * 0.1
    pointer.y += (targetPointer.y - pointer.y) * 0.1
    material.uniforms.u_point.value = pointer

    material.uniforms.u_time.value = clock.getElapsedTime()
    renderer.render(scene, camera)
    requestAnimationFrame(render)
}

function updateSceneSize() {
    material.uniforms.u_ratio.value = window.innerWidth / window.innerHeight
    material.uniforms.u_width.value = window.innerWidth
    renderer.setSize(container.clientWidth, container.clientHeight)
}
</script>

<div class='container'>
    <canvas id='canvas'></canvas>
</div>

<script context='module'>
    export const vertexShaderSource = `
        varying vec2 vUv;
        void main() {
            vUv = uv;
            gl_Position = vec4(position, 1.);
        }
    `

    export const fragmentShaderSource = `
        varying vec2 vUv;
        uniform float u_ratio;
        uniform float u_time;
        uniform float u_width;
        uniform float u_coloring;
        uniform float u_speed;
        uniform vec2 u_point;

        vec3 permute(vec3 x) { return mod(((x*34.0)+1.0)*x, 289.0); }
        float snoise(vec2 v){
            const vec4 C = vec4(0.211324865405187, 0.366025403784439,
            -0.577350269189626, 0.024390243902439);
            vec2 i = floor(v + dot(v, C.yy));
            vec2 x0 = v - i + dot(i, C.xx);
            vec2 i1;
            i1 = (x0.x > x0.y) ? vec2(1.0, 0.0) : vec2(0.0, 1.0);
            vec4 x12 = x0.xyxy + C.xxzz;
            x12.xy -= i1;
            i = mod(i, 289.0);
            vec3 p = permute(permute(i.y + vec3(0.0, i1.y, 1.0))
            + i.x + vec3(0.0, i1.x, 1.0));
            vec3 m = max(0.5 - vec3(dot(x0, x0), dot(x12.xy, x12.xy),
            dot(x12.zw, x12.zw)), 0.0);
            m = m*m;
            m = m*m;
            vec3 x = 2.0 * fract(p * C.www) - 1.0;
            vec3 h = abs(x) - 0.5;
            vec3 ox = floor(x + 0.5);
            vec3 a0 = x - ox;
            m *= 1.79284291400159 - 0.85373472095314 * (a0*a0 + h*h);
            vec3 g;
            g.x = a0.x * x0.x + h.x * x0.y;
            g.yz = a0.yz * x12.xz + h.yz * x12.yw;
            return 130.0 * dot(m, g);
        }

        vec3 hsv2rgb(vec3 c) {
            vec4 K = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
            vec3 p = abs(fract(c.xxx + K.xyz) * 6.0 - K.www);
            return c.z * mix(K.xxx, clamp(p - K.xxx, 0.0, 1.0), c.y);
        }

        float get_noise(vec2 uv, float t){
            float SCALE = 1.5;
            float noise = snoise(vec2(uv.x * .9 * SCALE, -uv.y * SCALE - t));
            SCALE = 1.;
            noise += 1. * snoise(vec2(uv.x * SCALE + 3. * t, uv.y * .8 * SCALE));
            noise += 1.;

            return noise;
        }

        float circle_s (vec2 dist, float radius) {
            return smoothstep(0., radius, pow(dot(dist, dist), .3) * .1);
        }

        void main () {
            vec2 uv = vUv;
            uv /= (1000.0 / u_width);
            uv.y /= u_ratio;

            vec2 mouse = vUv - u_point;
            mouse.y /= u_ratio;

            float t = u_time * u_speed;

            float noise = get_noise(uv, t);
            noise *= circle_s(mouse, 0.08);

            vec3 col = vec3(1.0, 171.0/255.0, 213.0/255.0);

            col = mix(col, vec3(1), smoothstep(2., .2, noise));

            gl_FragColor = vec4(col, .6);
        } 
    `
</script>

<style>
    .container {
        width: 100%;
        height: 100%;

        position: fixed;
        top: 0;
        left: 0;       
        z-index: -1;
    }

    #canvas {
        pointer-events: none;
    }
</style>