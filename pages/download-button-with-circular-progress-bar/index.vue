<template>
  <div class="download-circular-btn-container">
        <button :class="{ 'download-circular-btn': true, 'active': isDownloading }" @click="downloadCircularButton">
            <font-awesome-icon class="download-circular-icon" :icon="faDownload" />
            Download
            <div class="progress-wrapper">
                <div class="inner"></div>
                <div class="checkmark">
                    <span></span>
                    <span></span>
                </div>
                <div class="circle">
                    <div class="bar left">
                        <div class="progress"></div>
                    </div>
                    <div class="bar right">
                        <div class="progress"></div>
                    </div>
                </div>
            </div>
        </button>
  </div>
</template>

<script setup>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faDownload } from '@fortawesome/free-solid-svg-icons';

const isDownloading = ref(false);

const downloadCircularButton = () => {
    isDownloading.value = true;

};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');


.download-circular-btn-container {
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Poppins', sans-serif;
    min-height: 100vh;
}

.download-circular-btn {
    position: relative;
    width: 350px;
    height: 110px;
    background: #2ecc71;
    border-radius: 100px;
    color: #fff;
    font-size: 28px;
    font-weight: 500;
    border: none;
    outline: none;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: .7s ease-in-out;
}

.download-circular-btn.active {
    font-size: 0;
    width: 110px;
    background: #ededed;
}

.download-circular-btn .download-circular-icon {
    margin-right: 15px;
}

.download-circular-btn .progress-wrapper {
    position: absolute;
    width: 110px;
    height: 110px;
    transform: scale(0);
    transition: .7s;
    transition-delay: .5s;
}

.download-circular-btn.active .progress-wrapper {
    transform: scale(1);
}

.download-circular-btn .progress-wrapper .inner {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 80px;
    height: 80px;
    background: #fff;
    border-radius: 50%;
    z-index: 2;
    transition: 1s ease;
    transition-delay: 4s;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}

.download-circular-btn.active .progress-wrapper .inner {
    transform: translate(-50%, -50%) scale(0);
}

.download-circular-btn .progress-wrapper .bar {
    position: absolute;
    width: 100%;
    height: 100%;
    background: #ededed;
    border-radius: 50%;
    clip: rect(0, 110px, 110px, 55px);
}

.download-circular-btn .progress-wrapper .bar .progress {
    position: absolute;
    width: 100%;
    height: 100%;
    background: #2ecc71;
    border-radius: 50%;
    clip: rect(0, 55px, 110px, 0px);
    z-index: 1;
}

.download-circular-btn .circle .bar.left .progress {
    transition: 1.5s linear;
    transition-delay: 1s;
}   
.download-circular-btn.active .circle .bar.left .progress {
    transform: rotate(180deg);
}

.download-circular-btn .circle .bar.right {
    transform: rotate(180deg);
}

.download-circular-btn .circle .bar.right .progress {
    transition: 1.5s linear;
    transition-delay: 2.5s;
}

.download-circular-btn.active .circle .bar.right .progress {
    transform: rotate(180deg);
}

.download-circular-btn .progress-wrapper .checkmark {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    z-index: 2; 
}

.download-circular-btn .progress-wrapper .checkmark span {
    position: absolute;
    display: block;
    width: 30px;
    height: 7px;
    background: #fff;
    border-radius: 5px;
    transform-origin: left ;
    transition: .5s;
}

.download-circular-btn .progress-wrapper .checkmark span:first-child {
    top: 50px;
    left: 27px;
    width: 30px;
    transform: rotate(45deg) scaleX(0);
    transition-delay: 5s;
}

.download-circular-btn.active .progress-wrapper .checkmark span:first-child {
    transform: rotate(45deg) scaleX(1);
}

.download-circular-btn .progress-wrapper .checkmark span:last-child {
    top: 70px;
    left: 45px;
    width: 50px;
    transform: rotate(-45deg) scaleX(0);
    transition-delay: 5.5s;
}

.download-circular-btn.active .progress-wrapper .checkmark span:last-child {
    transform: rotate(-45deg) scaleX(1);
}
</style>