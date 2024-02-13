<script setup>
import { onMounted } from 'vue'
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";

// gsap работает только на onMounted
onMounted(() => {

    gsap.registerPlugin(ScrollTrigger);
    let tl = gsap.timeline()
    ScrollTrigger.create({
        animation: tl,
        trigger: '.reg',
        endTrigger: '.plpo',
        // pin: true,
        markers: true,
        scrub: true,
        start: 'top',
        end: 'center 150px'
        // pinSpacing: false
    })

    tl.to('.plpo', {
        duration: 5,
        scaleX: 1.2
    })
        .to('.plpo', {
            duration: 2,
            scale: 1.2
        })
        .to('.plpo', {
            duration: 2,
            scale: 1
        })
})
</script>
<template>
    <v-row justify="center">
        <v-col class="plpo" cols="10">

            Зарегистрируйся сейчас, иначе
            <h3>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
                dolore magna aliqua. Enim tortor at auctor urna nunc id cursus metus aliquam. Vel pretium lectus quam id
                leo. Sit amet porttitor eget dolor morbi non arcu. Lacus laoreet non curabitur gravida arcu ac tortor.
                Dignissim suspendisse in est ante in nibh. Pharetra magna ac placerat vestibulum lectus mauris. Leo vel
                <!-- fringilla est ullamcorper. Ipsum dolor sit amet consectetur adipiscing elit. Enim praesent elementum
                facilisis leo. Massa sapien faucibus et molestie ac feugiat. Id eu nisl nunc mi. Mi ipsum faucibus vitae
                aliquet nec ullamcorper sit amet. Dolor sit amet consectetur adipiscing elit. Sagittis purus sit amet
                volutpat consequat mauris nunc congue nisi. Feugiat pretium nibh ipsum consequat nisl. Mi bibendum neque
                egestas congue quisque. Tortor aliquam nulla facilisi cras fermentum odio eu feugiat. Rhoncus aenean vel
                elit scelerisque mauris pellentesque. Cursus sit amet dictum sit amet. Libero nunc consequat interdum varius
                sit amet. Vitae ultricies leo integer malesuada. Rhoncus aenean vel elit scelerisque. Fermentum odio eu
                feugiat pretium nibh ipsum consequat nisl vel. Magna fringilla urna porttitor rhoncus dolor purus. Etiam
                tempor orci eu lobortis elementum nibh. Odio tempor orci dapibus ultrices. Eget est lorem ipsum dolor sit
                amet consectetur adipiscing elit. Vel elit scelerisque mauris pellentesque pulvinar pellentesque habitant.
                Eros in cursus turpis massa tincidunt dui. Lorem ipsum dolor sit amet consectetur adipiscing. Maecenas sed
                enim ut sem. Mi eget mauris pharetra et ultrices neque ornare. Dignissim sodales ut eu sem integer vitae
                justo eget. Commodo nulla facilisi nullam vehicula ipsum a arcu cursus vitae. Consequat id porta nibh
                venenatis cras sed. Lorem sed risus ultricies tristique nulla aliquet enim tortor at. Sem fringilla ut morbi
                tincidunt augue interdum. In nibh mauris cursus mattis. Sagittis nisl rhoncus mattis rhoncus urna neque
            viverra. Ut enim blandit volutpat maecenas volutpat blandit aliquam etiam erat. Velit euismod in
            pellentesque massa placerat duis. Ultrices gravida dictum fusce ut placerat orci. Lectus proin nibh nisl
            condimentum id venenatis a. Sagittis eu volutpat odio facilisis mauris sit.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua. Enim tortor at auctor urna nunc id cursus metus aliquam. Vel pretium lectus quam id
            leo. Sit amet porttitor eget dolor morbi non arcu. Lacus laoreet non curabitur gravida arcu ac tortor.
            Dignissim suspendisse in est ante in nibh. Pharetra magna ac placerat vestibulum lectus mauris. Leo vel
            fringilla est ullamcorper. Ipsum dolor sit amet consectetur adipiscing elit. Enim praesent elementum
            facilisis leo. Massa sapien faucibus et molestie ac feugiat. Id eu nisl nunc mi. Mi ipsum faucibus vitae
            aliquet nec ullamcorper sit amet. Dolor sit amet consectetur adipiscing elit. Sagittis purus sit amet
            volutpat consequat mauris nunc congue nisi. Feugiat pretium nibh ipsum consequat nisl. Mi bibendum neque
            egestas congue quisque. Tortor aliquam nulla facilisi cras fermentum odio eu feugiat. Rhoncus aenean vel
            elit scelerisque mauris pellentesque. Cursus sit amet dictum sit amet. Libero nunc consequat interdum varius
            sit amet. Vitae ultricies leo integer malesuada. Rhoncus aenean vel elit scelerisque. Fermentum odio eu
            feugiat pretium nibh ipsum consequat nisl vel. Magna fringilla urna porttitor rhoncus dolor purus. Etiam
            tempor orci eu lobortis elementum nibh. Odio tempor orci dapibus ultrices. Eget est lorem ipsum dolor sit
            amet consectetur adipiscing elit. Vel elit scelerisque mauris pellentesque pulvinar pellentesque habitant.
            Eros in cursus turpis massa tincidunt dui. Lorem ipsum dolor sit amet consectetur adipiscing. Maecenas sed
            enim ut sem. Mi eget mauris pharetra et ultrices neque ornare. Dignissim sodales ut eu sem integer vitae
            justo eget. Commodo nulla facilisi nullam vehicula ipsum a arcu cursus vitae. Consequat id porta nibh
            venenatis cras sed. Lorem sed risus ultricies tristique nulla aliquet enim tortor at. Sem fringilla ut morbi
            tincidunt augue interdum. In nibh mauris cursus mattis. Sagittis nisl rhoncus mattis rhoncus urna neque
            viverra. Ut enim blandit volutpat maecenas volutpat blandit aliquam etiam erat. Velit euismod in
            pellentesque massa placerat duis. Ultrices gravida dictum fusce ut placerat orci. Lectus proin nibh nisl
            condimentum id venenatis a. Sagittis eu volutpat odio facilisis mauris sit.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua. Enim tortor at auctor urna nunc id cursus metus aliquam. Vel pretium lectus quam id
            leo. Sit amet porttitor eget dolor morbi non arcu. Lacus laoreet non curabitur gravida arcu ac tortor.
            Dignissim suspendisse in est ante in nibh. Pharetra magna ac placerat vestibulum lectus mauris. Leo vel
            fringilla est ullamcorper. Ipsum dolor sit amet consectetur adipiscing elit. Enim praesent elementum
            facilisis leo. Massa sapien faucibus et molestie ac feugiat. Id eu nisl nunc mi. Mi ipsum faucibus vitae
            aliquet nec ullamcorper sit amet. Dolor sit amet consectetur adipiscing elit. Sagittis purus sit amet
            volutpat consequat mauris nunc congue nisi. Feugiat pretium nibh ipsum consequat nisl. Mi bibendum neque
            egestas congue quisque. Tortor aliquam nulla facilisi cras fermentum odio eu feugiat. Rhoncus aenean vel
            elit scelerisque mauris pellentesque. Cursus sit amet dictum sit amet. Libero nunc consequat interdum varius
            sit amet. Vitae ultricies leo integer malesuada. Rhoncus aenean vel elit scelerisque. Fermentum odio eu
            feugiat pretium nibh ipsum consequat nisl vel. Magna fringilla urna porttitor rhoncus dolor purus. Etiam
            tempor orci eu lobortis elementum nibh. Odio tempor orci dapibus ultrices. Eget est lorem ipsum dolor sit
            amet consectetur adipiscing elit. Vel elit scelerisque mauris pellentesque pulvinar pellentesque habitant.
            Eros in cursus turpis massa tincidunt dui. Lorem ipsum dolor sit amet consectetur adipiscing. Maecenas sed
            enim ut sem. Mi eget mauris pharetra et ultrices neque ornare. Dignissim sodales ut eu sem integer vitae
            justo eget. Commodo nulla facilisi nullam vehicula ipsum a arcu cursus vitae. Consequat id porta nibh
            venenatis cras sed. Lorem sed risus ultricies tristique nulla aliquet enim tortor at. Sem fringilla ut morbi
            tincidunt augue interdum. In nibh mauris cursus mattis. Sagittis nisl rhoncus mattis rhoncus urna neque
            viverra. Ut enim blandit volutpat maecenas volutpat blandit aliquam etiam erat. Velit euismod in
            pellentesque massa placerat duis. Ultrices gravida dictum fusce ut placerat orci. Lectus proin nibh nisl
            condimentum id venenatis a. Sagittis eu volutpat odio facilisis mauris sit.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua. Enim tortor at auctor urna nunc id cursus metus aliquam. Vel pretium lectus quam id
            leo. Sit amet porttitor eget dolor morbi non arcu. Lacus laoreet non curabitur gravida arcu ac tortor.
            Dignissim suspendisse in est ante in nibh. Pharetra magna ac placerat vestibulum lectus mauris. Leo vel
            fringilla est ullamcorper. Ipsum dolor sit amet consectetur adipiscing elit. Enim praesent elementum
            facilisis leo. Massa sapien faucibus et molestie ac feugiat. Id eu nisl nunc mi. Mi ipsum faucibus vitae
            aliquet nec ullamcorper sit amet. Dolor sit amet consectetur adipiscing elit. Sagittis purus sit amet
            volutpat consequat mauris nunc congue nisi. Feugiat pretium nibh ipsum consequat nisl. Mi bibendum neque
            egestas congue quisque. Tortor aliquam nulla facilisi cras fermentum odio eu feugiat. Rhoncus aenean vel
            elit scelerisque mauris pellentesque. Cursus sit amet dictum sit amet. Libero nunc consequat interdum varius
            sit amet. Vitae ultricies leo integer malesuada. Rhoncus aenean vel elit scelerisque. Fermentum odio eu
            feugiat pretium nibh ipsum consequat nisl vel. Magna fringilla urna porttitor rhoncus dolor purus. Etiam
            tempor orci eu lobortis elementum nibh. Odio tempor orci dapibus ultrices. Eget est lorem ipsum dolor sit
            amet consectetur adipiscing elit. Vel elit scelerisque mauris pellentesque pulvinar pellentesque habitant. -->
        </h3>
    </v-col>
</v-row>
</template>
<style scoped>
.plpo {
    position: relative;

    height: 2000px;
    background-color: blue;

}</style>