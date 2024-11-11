<script setup>
    import { ref } from 'vue'

    const buttonText = ref("")

</script>

<template>
    <button class="mainButton" @click="clickAction">{{buttonText}}</button>
</template>

<style>
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
</style>