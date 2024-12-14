<template>
    <div class="confetti-button-container">
        <button class="confetti-btn" @click="confettiButton">
            <span>🎉</span>
            <span>Confetti</span>
        </button>
    </div>
</template>

<script setup>
import confetti from 'canvas-confetti';

const confettiButton = () => {
    confetti({
        particleCount: 300,
        spread: 100
    });
};
</script>

<style>
.confetti-button-container {
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    height: 100vh;
    width: 100vw;
}

.confetti-btn {
    background-color: #404663;
    color: #fff;
    border: 0;
    font-size: 2rem;
    font-weight: 400;
    padding: 0.5em 1.25em;
    border-radius: 0.5em;
    z-index: 999;
    position: relative;
    display: flex;
    gap: 0.5em;
    box-shadow:
        0px 1.7px 2.2px rgba(0, 0, 0, 0.02),
        0px 4px 5.3px rgba(0, 0, 0, 0.028),
        0px 7.5px 10px rgba(0, 0, 0, 0.035),
        0px 13.4px 17.9px rgba(0, 0, 0, 0.042),
        0px 25.1px 33.4px rgba(0, 0, 0, 0.05),
        0px 60px 80px rgba(0, 0, 0, 0.07);
    margin-bottom: 100px;
}

.confetti-btn span:first-child {
    margin-right: 10px;
}
</style>