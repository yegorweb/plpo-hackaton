<script setup>
import { onMounted, watch, ref } from "vue";
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { MotionPathPlugin } from "gsap/MotionPathPlugin";
import { useWindowSize } from '@vueuse/core'

const { width, height } = useWindowSize()

let one = ref(null)
let two = ref(null)
let three = ref(null)
let four = ref(null)
let five = ref(null)
let six = ref(null)
let seven = ref(null)

function placePosters(h = height.value, w = width.value) {
    // вычисляется через aspectRatio/posterHeight
    let cardWidth = 177
    one.value.style['left'] = String(w / 2 - cardWidth + 10) + 'px'

    two.value.style['left'] = String(w / 2 + 10) + 'px'

    three.value.style['top'] = String(60) + 'px'
    three.value.style['left'] = String(w / 2 - cardWidth - 20) + 'px'

    four.value.style['left'] = String(w / 2 + 10 + 10) + 'px'
    four.value.style['top'] = String(60) + 'px'

    five.value.style['top'] = String(125) + 'px'
    five.value.style['left'] = String(w / 2 - cardWidth - 20) + 'px'

    six.value.style['left'] = String(w / 2 + 10) + 'px'
    six.value.style['top'] = String(120) + 'px'

    seven.value.style['top'] = String(190) + 'px'
    seven.value.style['left'] = String(w / 2 - cardWidth + 20) + 'px'
}

watch([width, height], ([newWidth, newHeight]) => {
    placePosters(newHeight, newWidth)
})

// gsap работает только на onMounted
onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);
    gsap.registerPlugin(MotionPathPlugin);

    let tl = gsap.timeline()
    tl.to('.one', {
        motionPath: {
            // path: 'M2.49965 1.00003C-8.58625 208.317 348.639 216.895 1111.5 212',
            path: [{ x: width.value / 4, y: height.value / 8 }, { x: width.value / 2, y: height.value / 4 }],
            align: 'self',
            curviness: 2,
        },
        scale: 3,
        opacity: 0,
    }, '0');
    // tl.to('.two', {
    //     motionPath: {
    //         // path: 'M32.5004 1.5C-100 345 242 258 197.5 740',
    //         // path: [{ x: }]
    //         align: 'self',
    //         curviness: 2,
    //     },
    //     scale: 3,
    //     opacity: 0
    // }, '0');
    // tl.to('.three', {
    //     motionPath: { path: 'M1 590.5C528.186 406.338 672.84 286.149 756.5 0.5', align: 'self' },
    //     scale: 3,
    //     opacity: 0
    // }, '0');
    // tl.to('.four', {
    //     motionPath: { path: 'M962.5 587.5C883.212 399.073 576.063 257.558 1.5 1.5', align: 'self' },
    //     scale: 3,
    //     opacity: 0
    // }, '0')
    // tl.to('.five', {
    //     motionPath: { path: 'M546.5 2C968.329 418.51 317.348 380.629 0.5 457', align: 'self' },
    //     scale: 3,
    //     opacity: 0
    // }, '0')
    // tl.to('.six', {
    //     motionPath: { path: 'M304 1018.5C149 986 186.5 407.5 2 1.5', align: 'self' },
    //     scale: 3,
    //     opacity: 0
    // }, '0')

    ScrollTrigger.create({
        animation: tl,
        trigger: '.poster-container',
        start: '-=25%',
        end: '+=140%',
        scrub: 1.2,
        pin: true,
        anticipatePin: 1,
    })

    placePosters()
})
</script>
<template>
    <div class="poster-container">
        <div class="row">
            <div class="poster one" ref="one">
                1
            </div>
            <div class="poster two" ref="two">
                2
            </div>
            <div class="poster five" ref="five">
                5
            </div>
            <div class="poster seven" ref="seven">
                seven
            </div>
        </div>
        <div class="row">
            <div class="poster three" ref="three">
                3
            </div>
            <div class="poster four" ref="four">
                4
            </div>
            <div class="poster six" ref="six">
                six
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.poster {
    aspect-ratio: calc(210 / 297);
    height: 250px;
    margin: 5px;
    border-radius: 8px;
    overflow-x: hidden;
    overflow-y: hidden;
    position: absolute;
}

.one {
    z-index: 5;
    transform: rotate(-10deg);
    background-color: aquamarine;
}

.two {
    z-index: 101;
    transform: rotate(6deg);
    background-color: blue;
}

.three {
    z-index: 101;
    background-color: darkblue;
    transform: rotate(-8deg);
}

.four {
    z-index: 102;
    background-color: red;
    transform: rotate(8deg);
}

.five {
    z-index: 110;
    background-color: red;
    transform: rotate(-8deg);
}

.six {
    z-index: 104;
    background-color: hotpink;
    transform: rotate(4deg);
}

.seven {
    z-index: 111;
    background-color: goldenrod;
    transform: rotate(-8deg);
}

.poster-cover {
    aspect-ratio: calc(210 / 297);
    height: 200px;
}

.poster-container {
    display: flex;
    flex-direction: column;
    min-height: 100vh;

    .row {
        width: 100%;
    }
}
</style>