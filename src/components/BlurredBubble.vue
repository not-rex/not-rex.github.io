<script setup>
import { gsap } from 'gsap';
import { onMounted } from 'vue';

onMounted(() => {

    gsap.to("#circle1", {
      duration: 10,
      repeat: -1,
      yoyo: true,
      rotation: 300,
      transformOrigin: "100px 60%",
      ease: "power1.inOut"
    });

    gsap.to("#circle2", {
      duration: 8,
      repeat: -1,
      yoyo: true,
      rotation: 380,
      transformOrigin: "100px 60%",
      ease: "power1.inOut"
    });

    gsap.to("#circle3", {
      duration: 11,
      repeat: -1,
      yoyo: true,
      rotation: 280,
      transformOrigin: "80px 60%",
      ease: "power1.inOut"
    });

});

</script>

<template>
    <div class="orbit-container">
      <div class="circle" id="circle1"></div>
      <div class="circle" id="circle2"></div>
      <div class="circle" id="circle3"></div>
    </div>
  </template>
  
  <style>
    .orbit-container {
        width: 100%;
        height: 100%;
        margin: auto;
        display: flex;
        justify-content: right;
        align-items: center;
        position: absolute;
        top: 0;
        right: 0;
        z-index: -1;
        filter: blur(70px);
        overflow: hidden;
        padding-right: 15vw;
        opacity: 100%;
    }
  
    .circle {
      position: absolute;
      width: 10em;
      height: 10em;
      border-radius: 50%;
      z-index: 1;
    }
    
    #circle1{
        background-color: #FF5335;
        width: 25em;
        height: 25em;
        animation: orbit1 10s linear infinite, colorChange1 20s linear infinite;
    }

    #circle2{
        background-color: #3E92A3;
        width: 20em;
        height: 20em;
        animation: orbit2 8s linear infinite, colorChange2 20s linear infinite;
    }

    #circle3{
        background-color: #FF8303;
        width: 16em;
        height: 16em;
        animation: orbit3 6s linear infinite, colorChange3 20s linear infinite;
    }

    /*
    @keyframes colorChange1 {
    0% { background-color: #FFB3BA; }
    25% { background-color: #BAE1FF; }
    50% { background-color: #C4FAF8; }
    75% { background-color: #FBE4FF; }
    100% { background-color: #FFB3BA; }
    }

    @keyframes colorChange2 {
    0% { background-color: #FFDFBA; }
    25% { background-color: #FFFFBA; }
    50% { background-color: #BAFFC9; } 
    75% { background-color: #BAE1FF; }
    100% { background-color: #FFDFBA; }
    }

    @keyframes colorChange3 {
    0% { background-color: #FFCBA4; }
    25% { background-color: #FFB3BA; }
    50% { background-color: #FFFFBA; }
    75% { background-color: #C4FAF8; }
    100% { background-color: #FFCBA4; }
    }
    */

    .orbit-container::after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      backdrop-filter: blur(10px);
    }

  </style>
  