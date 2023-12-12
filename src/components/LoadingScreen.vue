<template>
    <div class="loading-screen">
      Loading...
    </div>
  </template>
  
  <script>
    export default {
        name: "LoadingScreen"
    };
  </script>
  
  <style>
  .loading-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }
  </style>
  