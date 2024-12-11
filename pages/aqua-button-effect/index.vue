<template>
    <div class="aqua-container">
        <a href="#" class="aqua-button">Aqua Water</a>
    </div>
</template>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.aqua-container {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    width: 100vw;
    background: #eee;
}

.aqua-button {
    position: relative;
    padding: 30px 80px;
    font-size: 30px;
    text-decoration: none;
    text-transform: uppercase;
    color: #444;
    box-shadow: inset 0 10px 5px rgba(0, 0, 0, 0.05),
    0 25px 8px rgba(0, 0, 0, 0.05),
    0 20px 15px rgba(0, 0, 0, 0.05),
    inset 0 -10px 15px rgba(255, 255, 255, 0.9); 
    border-radius: 550px;
}

.aqua-button::before {
    content: '';
    position: absolute;
    top: 18px;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 15px;
    width: 60%;
    height: 10px;
    background: #ffffff;
}
</style>