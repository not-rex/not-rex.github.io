<script setup>

import { useRouter } from 'vue-router';

const router = useRouter();

const goHome = () => {
  router.push('/');
};

</script>

<template>
    <div class="topnav">
        <a @click="goHome">PORTFOLIO</a>
        <!--<a @click="toggleLanguage" class="split">EN / 中</a>-->
        <hr class="btmline">
    </div>
</template>

<style scoped>
.topnav {
  overflow: hidden;
  height: 70px;
  position: fixed;
  top: 0;
  width: 100%;
  background-color: rgba(11, 11, 11, 0.5);
  -webkit-backdrop-filter: blur(30px);
  backdrop-filter: blur(30px);
  z-index: 100;
}

.topnav a {
  float: left;
  color: beige;
  text-align: center;
  padding: 25px 25px;
  text-decoration: none;
  font-size: 17px;
  padding-left: 3%;
  transition: color 0.3s;
}

.topnav a:hover {
  color: rgba(255, 255, 255, 0.384);
}

.topnav a.split {
    float: right;
    padding-right: 3%;
}

.btmline {
  border: 0.5px solid beige;
  width: 95%;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  margin: 0;
  opacity: 0%;
}
</style>