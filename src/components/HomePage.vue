<script setup>
import { onMounted, ref } from 'vue'
import { WOW } from 'wowjs';
import 'animate.css';

const userName = ref("Harrison Lan")

onMounted(() => {
  new WOW().init();
});

</script>

<template>
    
    <div class="centertitle">
        <h1 class="mainTitle subMain">Hey, I am</h1>
        <h1 class="mainTitle">{{ userName }}</h1>
        <h3 class="subTitle">Located at not-rex.github.io</h3>
    </div>

    <div class="body1">
        <h1>So ... What can I do?</h1>
        <br>
        <p>Full Stack Web Developer specialise in UI/UX</p>
        <p>Unity Developer</p>
        <p>Knowlege in C++ Matlab and Python</p>
    </div>

    <div class="body2">
        <h1>Projects</h1>
        <br>
        <p>...</p>
    </div>

</template>

<style scoped>

.centertitle {
    height: 100vh;
    padding-top: 5vh;
    padding-left: 10%;
    text-align: left;
    font-size: 80px;
    line-height: 200%;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.mainTitle {
    margin: 0;
    padding: 0;
}

.subMain{
    font-size: 80px;
    line-height: 120%;
    padding-left: 5px;
}

.subTitle{
    padding-top: 10px;
    font-size: 20px;
    line-height: 180%;
    color:rgb(70, 70, 65);
    padding-left: 10px;
}


.body1{
    font-size: 40px;
    padding-left: 10%;
    text-align: left;
    height: 85vh;
}

.body2{
    font-size: 40px;
    padding-left: 10%;
    text-align: left;
    height: 85vh;
}

</style>