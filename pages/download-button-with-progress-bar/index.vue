<template>
    <div :class="{'download-button' : true, 'active': isDownloading}" @click="downloadButton">
        <div class="content">
            <box-icon class="download-btn-icon" :name="icon" color='#fff'></box-icon>
            <span class="download-btn-text">{{ label }}</span>
        </div>
    </div>
</template>

<script setup>
import 'boxicons';
const isDownloading = ref(false);
const label = ref('Download');
const icon = ref('cloud-download');

const downloadButton = () => {
    isDownloading.value = true;

    setTimeout(() => {
        isDownloading.value = false;
        label.value = 'Completed';
        icon.value = 'check-circle';
    }, 6000);
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

* {
    font-family: 'Poppins', sans-serif;
}

.download-button {
    position: absolute;
    bottom: 60%;
    left: 50%;
    transform: translate(-50%, 50%);
    height: 95px;
    width: 360px;
    background: #080c64;
    border-radius: 20px;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
    transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    cursor: pointer;
    overflow: hidden;
}

.download-button.active {
    height: 20px;
    width: 500px;
}

.download-button::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    height: 100%;
    width: 100%;
    border-radius: 20px;
    background: #0066ff;
}

.download-button.active::before {
    animation:  layer 6s ease-in-out forwards;
}

@keyframes layer {
   100%{
         left: 0%;
   }

}

.download-button .content {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #fff;
    transition: all 0.2s ease;
    transition-delay: 0.2s;
}

.download-button.active .content {
    transform: translateY(60px);
}

.download-button .download-btn-icon {
    width: 40px;
    height: 100%;
    margin-right: 20px;
}

.download-button .download-btn-text {
    font-size: 1.5rem;
}
</style>