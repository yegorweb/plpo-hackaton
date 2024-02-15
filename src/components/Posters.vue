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
    /**
     * 70% - образуют рамку для текста, увеличились в 3.5 раза и opacity: 0.95
     * 100% - расходятся прямолинейно, opacity: 0
     *  */
    tl.to('.one', {
        keyframes: {
            '25%': {
                x: width.value / 4
            },
            '70%': {
                x: width.value / 2.5, y: 100, opacity: 0.95, scale: 3.5,
            },
            '100%': { x: width.value / 2, opacity: 0, },
            easeEach: 'sine.out'
        },
    }, '0');
    tl.to('.two', {
        keyframes: {
            '70%': {
                y: height.value * 5 / 6, opacity: 0.95, x: width.value / 6, scale: 3.5,
            },
            '100%': { y: height.value * 1.2, x: width.value / 6, opacity: 0 },
            easeEach: 'sine.out'

        },
    }, '0');
    tl.to('.three', {
        keyframes: {
            '70%': { x: width.value / 4, y: -height.value / 4 * 3, scale: 3.5, opacity: 0.95 },
            '100%': { x: width.value / 3, y: -height.value, opacity: 0 },
            easeEach: 'sine.out'
        },
    }, '0');
    tl.to('.four', {
        keyframes: {
            '70%': { x: -width.value / 3, y: -height.value / 1.5, scale: 3.5, opacity: 0.95 },
            '100%': { x: -width.value / 2, y: -height.value, opacity: 0 },
            easeEach: 'sine.out'
        },
    }, '0')
    tl.to('.five', {
        keyframes: {
            '70%': {
                y: height.value * 3 / 4, x: -200, opacity: 0.95, scale: 3.5,
            },
            '100%': { y: height.value * 1.2, opacity: 0 },
            easeEach: 'sine.out'
        },
    }, '0')
    tl.to('.six', {
        keyframes: {
            '70%': { y: -height.value / 4 * 3, scale: 3.5, opacity: 0.9 },
            '100%': { y: -height.value, opacity: 0 },
            easeEach: 'sine.out'
        },
    }, '0')
    tl.to('.seven', {
        keyframes: {
            '70%': {
                x: -width.value / 3.5, y: 100, opacity: 0.95, scale: 3.5,
            },
            '100%': { x: -width.value / 2, opacity: 0, },
            easeEach: 'sine.out'
        },
    }, '0');

    tl.to('.last-message', {
        keyframes: {
            '25%': {
                opacity: 0
            },
            '70%': {
                opacity: 0.96
            },
            '100%': { opacity: 1, },
            easeEach: 'sine.out'
        },
    }, '0')

    ScrollTrigger.create({
        animation: tl,
        trigger: '.poster-container',
        start: '-=25%',
        end: '+=140%',
        scrub: 1.125,
        pin: true,
        anticipatePin: 1,
    })

    placePosters()
})
</script>
<template>
    <div class="first-message">
        <span>
            Готовы сделать нам постер за 20 тысяч рублей? Офигенная сделка, не правда ли? Вот бы кто хакатон по веб
            разработке в Глазове провёл, мы бы там всех сделали.
        </span>
    </div>
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
        <div class="last-message">
            <span>
                Ваш постер попадёт в топ 10 лучших Глазова и вы станете самым крутым дизайнером планеты
            </span>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.poster {
    aspect-ratio: calc(210 / 297);
    height: 250px;
    margin: 5px;
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
    z-index: 109;
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

.last-message {
    opacity: 0;
    width: 100%;
    position: absolute;
    top: 25%;
    display: flex;
    justify-content: center;

    span {
        max-width: 40%;
        text-align: center;
        color: rgba(0, 0, 0, 0.7);
        font-weight: 600;
        font-size: 20px;
    }
}

.first-message {
    width: 100%;
    margin-bottom: 40px;
    display: flex;
    justify-content: center;

    span {
        max-width: 40%;
        text-align: center;
        color: rgba(0, 0, 0, 0.7);
        font-weight: 600;
        font-size: 20px;
    }
}
</style>