<template>
    <div class="magnetic-button-container">
        <a ref="magneticRef" href="#" class="magnetic-button" @mousemove="(e) => magnetic(e, 1)" @mouseout="() => magneticOut(1)" :style="{ '--clr': '#ff5d4b' }">
            <span>Magnetic Button</span>
        </a>
        <a ref="magneticRef2" href="#" class="magnetic-button" @mousemove="(e) => magnetic(e, 2)" @mouseout="() => magneticOut(2)" :style="{ '--clr': '#0088ff' }">
            <span>Magnetic Button</span>
        </a>
    </div>
</template>

<script setup>
const magneticRef = ref(null);
const magneticRef2 = ref(null);

const magnetic = (e, refNum) => {
    const elementRef = refNum === 1 ? magneticRef : magneticRef2;
    let x = e.offsetX;
    let y = e.offsetY;
    let btnWidth = elementRef.value.clientWidth;
    let btnHeight = elementRef.value.clientHeight;
    let transX = (x - btnWidth / 2);
    let transY = (y - btnHeight / 2);

    elementRef.value.style.transform = `translateX(${transX}px) translateY(${transY}px)`;

    let mx = e.pageX - elementRef.value.offsetLeft;
    let my = e.pageY - elementRef.value.offsetTop;

    elementRef.value.style.setProperty('--mouse-x', `${mx}px`);
    elementRef.value.style.setProperty('--mouse-y', `${my}px`);
}

const magneticOut = (refNum) => {
    const elementRef = refNum === 1 ? magneticRef : magneticRef2;
    elementRef.value.style.transform = ``;
}


</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

.magnetic-button-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    /* background: #ff5d4b; */
    font-family: 'Poppins', sans-serif;
    gap: 50px;
}

.magnetic-button {
    position: relative;
    width: 250px;
    padding: 15px 20px;
    background: #333;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1em;
    text-transform: uppercase;
    font-weight: 600;
    letter-spacing: 0.1em;
    cursor: pointer;
    text-decoration: none;
    border-radius: 10px;
    transition: transform 0.1s ;
    overflow: hidden;
}

.magnetic-button span {
    position: relative;
    pointer-events: none;
    color: rgba(255, 255, 255, 0.25);
    transition: 0.5s;
}

.magnetic-button:hover span {
    color: rgba(255, 255, 255, 1);
}

.magnetic-button::before {
    content: '';
    position: absolute;
    top: var(--mouse-y);
    left: var(--mouse-x);
    transform: translate(-50%, -50%);
    background: var(--clr);
    width: 0px;
    height: 0px;
    border-radius: 50%;
    transition: 1s, left 0s, top 0s;

}

.magnetic-button:hover::before {
    width: 150px;
    height: 150px;
}
</style>