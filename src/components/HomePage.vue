<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { Draggable } from "gsap/Draggable";
import { TextPlugin } from "gsap/TextPlugin";

gsap.registerPlugin(ScrollTrigger);
gsap.registerPlugin(Draggable);
gsap.registerPlugin(TextPlugin);

const userName = ref("Harrison Lan");

const animateGreetMessage = () => {
  const messages = [
    "👋 Hey! I am",
    "👋 嗨! 我是",
    "👋 おい! 私は",
    "🦈 Hallå! jag är",
    "👋 ¡Ey! Soy",
    "يا! أنا أكون 👋",
    "👋 Hé! Je suis",
    "👋 Привет! Я",
    "👋 Ei! Eu sou",
  ];

  let currentIndex = 0;

  const animate = () => {
    const message = messages[currentIndex];
    const tl = gsap.timeline();

    tl.to(".subMain", { 
      duration: 1, 
      text: "",
      onComplete: () => {
        gsap.to(".subMain", { duration: 2, text: message, ease: "none" });
      }
    });

    currentIndex = (currentIndex + 1) % messages.length;
    setTimeout(animate, 6000);
  };

  animate();
};


const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  });
};

const scrollToSepLine = () => {
  const sepLineElement = document.querySelector('.sep-line');
  if (sepLineElement) {
    const sepLineOffset = sepLineElement.offsetTop;
    window.scrollTo({
      top: sepLineOffset,
      behavior: 'smooth'
    });
  }
};


onMounted(() => {

    animateGreetMessage();

    gsap.to(".titleAnimate", {
        y: -100,
        scrollTrigger: {
            trigger: ".titleAnimate",
            start: "top center",
            end: "bottom top",
            scrub: 1,
    },
    });

    Draggable.create('.mainButton', {
        type: 'x,y',
        bounds: document.getElementById("centertitle"),
    });

  gsap.to(".body1Title", {
    y: -100,
    scrollTrigger: {
      trigger: ".body1Title",
      start: "top center",
      end: "bottom top",
      scrub: 1,
    },
  });

  gsap.to(".subMain", {
    opacity: 0,
    scrollTrigger: {
      trigger: ".subMain",
      start: "top 30%",
      end: "bottom 30%",
      scrub: 1,
    },
  });

  gsap.to(".b1p1", {
    y: -100,
    scrollTrigger: {
      trigger: ".b1p1",
      start: "top center",
      end: "bottom top",
      scrub: 1,
    },
  });

  gsap.to(".b1p2", {
    y: -200,
    scrollTrigger: {
      trigger: ".b1p2",
      start: "top center",
      end: "bottom top",
      scrub: 1,
    },
  });

  gsap.to(".b1p3", {
    y: -300,
    scrollTrigger: {
      trigger: ".b1p3",
      start: "top center",
      end: "bottom top",
      scrub: 1,
    },
  });

    let lastScroll = 0;
    const maxSkew = 25;

    ScrollTrigger.create({
        trigger: '.scroll-container',
        start: 'top top',
        end: '500%',
        pin: true,
        scrub: 1.5,
        animation: gsap.to('.body2', {
            x: '-500vh',
            ease: 'none'
        }),
        onUpdate: (self) => {
            const scroll = self.scroll();
            const velocity = scroll - lastScroll;
            lastScroll = scroll;

            let skewValue = velocity * 1.5;
            skewValue = Math.min(Math.max(skewValue, -maxSkew), maxSkew);

            gsap.to('.body2', {
                skewX: skewValue,
                ease: 'power3.out',
                overwrite: 'auto'
            });
        },
        onEnter: () => resetSkew(),
        onLeave: () => resetSkew(),
        onEnterBack: () => resetSkew(),
        onLeaveBack: () => resetSkew(),
    });

    function resetSkew() {
        gsap.to('.body2', {
            skewX: 0,
            ease: 'power3.out'
        });
    }
  
});
</script>

<template>
    
    <div class="centertitle">
        <!--<h1 class="mainTitle subMain">{{ greetMessage }}</h1>-->
        <h1 class="mainTitle subMain"></h1>
        <h1 class="mainTitle titleAnimate">{{ userName }}.</h1>
        <h3 class="subTitle"><i class="fas fa-map-marker-alt"></i> Adelaide, Australia</h3>
        <button class="mainButton" @click="scrollToSepLine">Explore</button>
    </div>
    <!--<img class="arrowdown" src="../assets/arrowdown.svg">-->
    <hr class="sep-line">
    <div class="body1">
        <h1 class="body1Title">So ... What can I do?</h1>
        <br>
        <div class="cardContainer">
            <div class="card b1p1">
                <p>Unity Developer</p>
            </div>
            <div class="card b1p2">
                <p>Full Stack Web Developer</p>
                <p>specialise in UI/UX</p>
            </div>
            <div class="card b1p3">
                <p>Knowlege in C++ Python</p>
                <p>C# Matlab and more</p>
            </div>
        </div>
    </div>

    <div class="scroll-container">
        <div class="body2">
            <h1 class="body2Title">Projects.Projects.Projects.Projects.Projects.Projects.Projects.Projects.Projects.</h1>
        </div>
    </div>

    <div class="footer">
        <div class="footerObjects">
            <button class="backTopButton" @click="scrollToTop">Back to Top</button>
        </div>
    </div>

</template>

<style scoped>

html {
  font-size: 16px;
  scroll-behavior: smooth;
}

.centertitle {
    height: 110vh;
    padding-top: 0vh;
    padding-left: 10%;
    text-align: left;
    font-size: 5rem;
    line-height: 200%;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.hr{
    width: 80%;
    margin: auto;
}

.mainTitle {
    margin: 0;
    padding: 0;
    padding-top: 1rem;
}

.subMain{
    font-size: 5rem;
    line-height: 100%;
    padding-left: 0.3rem;
    color: rgb(246, 246, 233);
}

.subTitle{
    font-size: 1.25rem;
    color:rgb(70, 70, 65);
    padding-left: 0.6rem;
    padding-bottom: 1rem;
    line-height: 100%;
    margin-top: 0vh;
}

.mainButton{
    position: relative;
    overflow: hidden;
    background-color: transparent;
    border: 3px solid rgb(246, 246, 233);
    color: rgb(246, 246, 233);
    border-radius: 30px;
    width: 150px;
    height: 50px;
    font-weight: 600;
    font-size: 25px;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    cursor: pointer;
    transition: background-color 0.5s;
    z-index: 1;
}

.arrowdown{
    width: 3rem;
    height: 3rem;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    top: -23vh;
}

.mainButton:hover {
    background-color: rgb(246, 246, 233); 
    color: rgb(21, 21, 21);
}

.body1Title{
    font-size: 4.5rem;
    width: 80%;
    margin: auto;
    text-align: center;
}

.body1{
    padding-top: 10vh;
    height: 100vh;
    width: 100%;
    overflow: hidden;
}
.cardContainer {
    gap: 20px;
    font-size: 2.5rem;
    padding-top: 10vh;
}

.b1p1{
    padding-left: 20vw;
}
.b1p2{
    padding-left: 20vw;
    text-align: center;
    width: 100%;
    margin: auto;
    padding-top: 3vh;
}
.b1p3{
    float: left;
    padding-left: 20vw;
    text-align: center;
    padding-top: 3vh;
}

.scroll-container {
    width: 100%;
    height: 100vh;
    overflow: hidden;
}

.body2Title {
    padding-top: 10vh;
    font-size: 15rem;
    color: rgba(82, 82, 82, 0.122);
    z-index: -1;
    text-align: right;
    width: 500vw;
}

.body2{
    font-size: 100px;
    height: 80vh;
    color:rgb(246, 246, 233);
    width: 500vw;
    overflow: hidden;
    transform-origin: left center;
    transition: transform 0.1s ease-out;
}
.sep-line {
    width: 80%;
    margin-left: auto;
    margin-right: auto;
    border: none;
    height: 4px;
    background-color: #333;
    position: relative;
    top: -10vh;
}

.footer{
    background-color: beige;
    height: 30vh;
}

.footer-rights{
    color: rgb(34, 34, 34);
    font-size: 5rem;
    font-weight: 300;
    padding-left: 20px;
}

.footerObjects{
    padding-top: 20vh;
    padding-right: 3vw;
    float: right;
}

.backTopButton{
    position: relative;
    overflow: hidden;
    background-color: transparent;
    border: 3px solid rgb(93, 92, 77);
    color: rgb(93, 92, 77);
    border-radius: 30px;
    width: 200px;
    height: 50px;
    font-weight: 600;
    font-size: 25px;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    cursor: pointer;
    transition: background-color 0.5s;
}

.backTopButton:hover {
    background-color: rgb(93, 92, 77); 
    color: rgb(246, 246, 233);
}

@keyframes blink {
  0% { opacity: 0; }
  50% { opacity: 0.3; }
  100% { opacity: 0; }
}

.subMain::after {
  content: "|";
  animation: blink 1s step-start 0s infinite;
}

@media (max-width: 768px) {

}

</style>