<script>

</script>


<template>

    <div class="login-container">
        <div class="input-container">
            <input type="text" id="account" v-model="account" placeholder="Account">
        </div>
        <div class="input-container">
            <input type="password" id="password" v-model="password" placeholder="Password">
        </div>
        <button class="login-button" @click="clickAction">Login</button>

    </div>

</template>
  
<style scoped>

.sign-in{
    font-size: 1.5rem;
}

.login-button{
    position: relative;
    overflow: hidden;
    background-color: transparent;
    border: 1px solid rgb(246, 246, 233);
    color: rgb(246, 246, 233);
    border-radius: 30px;
    width: 100px;
    height: 30px;
    font-size: 16px;
    align-items: center;
    cursor: pointer;
    transition: background-color 0.5s;
    z-index: 1;
    margin-top: 1em;
}
.login-button:hover {
    background-color: rgb(246, 246, 233); 
    color: rgb(21, 21, 21);
}

.login-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    color: rgb(246, 246, 233);
}

.input-container {
    margin-bottom: 20px;
}

.input-container input {
    color:rgb(246, 246, 233);
    font-size: 1rem;
    padding: 10px;
    border: none;
    border-bottom: 1px solid rgb(246, 246, 233);
    background-color: transparent;
    outline: none;
    width: 100%;
}

.input-container input::placeholder {
    color: rgb(246, 246, 233);
}

</style>