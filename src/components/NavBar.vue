<script setup>


</script>

<template>
    <div class="topnav">
        <a>PORTFOLIO</a>
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
  background-color:rgb(21, 21, 21);
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
}

.topnav a:hover {
  color: rgb(143, 143, 143);
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
}
</style>