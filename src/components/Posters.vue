<script setup>
import { onMounted, watch, ref } from "vue";
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { MotionPathPlugin } from "gsap/MotionPathPlugin";
import { useWindowSize } from '@vueuse/core'
import line from "../assets/line.svg"
import circle from "../assets/circle.svg"
import dark_trapezoid from "../assets/dark_trapezoid.svg"
import red_triangle from "../assets/red_triangle.svg"

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
                opacity: 0,
                scale: 1,
            },
            '70%': {
                opacity: 0.96,
                scale: 1.4,

            },
            '100%': { opacity: 1, scale: 1, },
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
    <div class="container">


        <div class="first-message">

            <h1>Создай <span>лу</span>чшую афишу <span>!</span> </h1>
            <!-- <img :src="circle" alt=""> -->
        </div>
        <div class="poster-container">
            <div class="row">
                <div class="poster one" ref="one">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/65c99a09437fede9d4afea9c.jpg">
                </div>
                <div class="poster two" ref="two">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/65c3b32e437fede9d4afe354.jpg">
                </div>
                <div class="poster five" ref="five">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/659a2b1897a5215f86585a4c.jpg" alt="">
                </div>
                <div class="poster seven" ref="seven">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/65bbe5f904c877c4408d050f.jpg" alt="">
                </div>
            </div>
            <div class="row">
                <div class="poster three" ref="three">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/65aa271a9bff79a9d86993b1.jpg">
                </div>
                <div class="poster four" ref="four">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/65c09981437fede9d4afdfff.jpg" alt="">
                </div>
                <div class="poster six" ref="six">
                    <img src="https://goroda-img.storage.yandexcloud.net/plakat-city/65a926859bff79a9d869901a.jpg">
                </div>

            </div>
            <div class="last-message">
                <h1>Выиграй <span>приз!</span> </h1>
                <!-- <img :src="line" alt="" class="line">
                <img :src="dark_trapezoid" alt="" class="dark_trapezoid">
                <img :src="red_triangle" alt="" class="red_triangle"> -->

            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.container {
    background: #EAEAC3;
}

img {
    user-drag: none;
    -webkit-user-drag: none;
    user-select: none;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
}

.poster {
    aspect-ratio: calc(210 / 297);
    height: 250px;
    margin: 5px;
    overflow-x: hidden;
    overflow-y: hidden;
    position: absolute;

    img {
        aspect-ratio: calc(210 / 297);
        height: 250px;
    }
}

.one {
    z-index: 5;
    transform: rotate(-10deg);
}

.two {
    z-index: 101;
    transform: rotate(6deg);
}

.three {
    z-index: 101;
    transform: rotate(-8deg);
}

.four {
    z-index: 102;
    transform: rotate(8deg);
}

.five {
    z-index: 110;
    transform: rotate(-8deg);
}

.six {
    z-index: 104;
    transform: rotate(4deg);
}

.seven {
    z-index: 109;
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
    height: 50dvh;
    position: relative;

    display: flex;
    justify-content: center;
    align-items: center;

    h1 {
        font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);
        padding: 10px;
        color: #EAEAC3;
        background: black;
        text-transform: uppercase;
        font-weight: 600;

        span {
            color: #F90007;
        }
    }

    .line {
        position: absolute;
        top: 10%;
        right: 10%;
        width: 20%;
    }

    .red_triangle {
        position: absolute;
        bottom: 10%;
        left: 10%;
        width: 20%;
    }

    .dark_trapezoid {
        position: absolute;
        bottom: -30%;
        left: 50%;
        width: 20%;
    }

}

.first-message {
    width: 100%;
    margin-bottom: 40px;
    display: flex;
    justify-content: center;
    position: relative;

    transform: rotate(-1deg);

    h1 {
        font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);
        padding: 10px;
        color: #EAEAC3;
        background: black;
        text-transform: uppercase;
        font-weight: 600;

        span {
            color: #F90007;
        }
    }

    img {
        position: absolute;
        left: 10%;
        bottom: 0%;
        width: 5%;
    }


}</style>