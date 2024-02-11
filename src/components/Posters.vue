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
        motionPath: { path: 'M573 260C240.69 222.261 104.213 172.094 1 1', align: 'self' },
        scale: 3
    }, '0');
    tl.to('.two', {
        motionPath: { path: 'M1 260C333.31 222.261 469.787 172.094 573 1', align: 'self' },
        scale: 3
    }, '0');
    tl.to('.three', {
        motionPath: { path: 'M573 1C240.69 38.7389 104.213 88.9059 1 260', align: 'self' },
        scale: 3
    }, '0');
    tl.to('.four', {
        motionPath: { path: 'M1 1C333.31 38.7389 469.787 88.9059 573 260', align: 'self' },
        scale: 3
    }, '0')

    ScrollTrigger.create({
        animation: tl,
        trigger: '.poster-container',
        start: '-=25%',
        end: '+=25%',
        scrub: 1.5,
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
        // display: flex;
        // justify-content: center;
    }
}
</style>