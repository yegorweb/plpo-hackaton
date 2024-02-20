<script setup>
gsap.from(".sponsor", {
  duration: 2,
  scale: 0.5, 
  opacity: 0, 
  delay: 0.5, 
  stagger: 0.2,
  ease: "elastic", 
});

document.querySelectorAll(".sponsor").forEach(function(sponsor) {
    sponsor.addEventListener("click", function() {
    gsap.to(".sponsor", {
      duration: 0.5, 
      opacity: 0, 
      y: -100, 
      stagger: 0.2,
      ease: "back.in"
    });
  });
});
</script>
<template>
    <div class="plpo">
        <h1 class="text-center title">Спонсоры</h1>
        <div style="height: 25dvh; background:#EAEAC3; overflow: scroll;" class="d-flex align-center justify-md-center">
            
            <div class="sponsor">
                <img src="../assets/bastion.jpg" alt="">
            </div>
            
           
            <div class="sponsor">
                <img src="../assets/bk.png" alt="">
            </div>
            <div class="sponsor">
                <img src="../assets/plpo.png" alt="">
            </div>
            <div class="sponsor">
                <img src="../assets/qbit.png" alt="">
            </div>
            <div class="sponsor">
                <img src="../assets/giv.png" alt="">
            </div>
            <div class="sponsor">
                <img src="../assets/trik.png" alt="">
            </div>
            <div class="sponsor">
                <img src="../assets/pro.png" alt="">
            </div>

        </div>
        <div style="height: 35dvh;">

        </div>


    </div>
</template>
<style scoped>
.plpo {

    height: 67dvh;
}

img {
    max-width: 150px;
    margin: 10px;
}

.title {
    font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);
    background: #EAEAC3;
    text-transform: uppercase;
    font-weight: 600;
}
</style>