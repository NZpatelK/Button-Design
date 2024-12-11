<template>
    <div class="glassmorphism-button-container">
        <div class="inner-container">
            <div class="glassmorphism-btn">
                <a href="#"> glassmorphism button </a>
            </div>
            <div class="glassmorphism-btn">
                <a href="#"> glassmorphism button </a>
            </div>
        </div>
    </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap');

.glassmorphism-button-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    width: 100vw;
    background: #034977;
    font-family: 'Poppins', sans-serif;
}

.glassmorphism-button-container .inner-container {
    width: 600px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.glassmorphism-btn {
    position: relative;
    width: 350px;
    height: 80px;
    margin: 20px;
}

.glassmorphism-btn a {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba(255, 255, 255, 0.05);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 10px;
    color: #fff;
    z-index: 1;
    font-weight: 400;
    font-size: 1.2em;
    text-transform: capitalize;
    letter-spacing: 1px;
    text-decoration: none;
    overflow: hidden;
    transition: 0.5s;
    backdrop-filter: blur(15px);
}

.glassmorphism-btn:hover a {
    letter-spacing: 3px;
}

.glassmorphism-btn a::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 50%;
    height: 100%;
    background: linear-gradient(to left, rgba(255, 255, 255, 0.15), transparent);
    transform: skewX(45deg) translateX(0);
    transition: 0.5s;
}

.glassmorphism-btn:hover a::before {
    transform: skewX(45deg) translateX(200%);
}

.glassmorphism-btn::before {
    content: '';
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: -5px;
    width: 50px;
    height: 10px;
    background: #00ccff;
    box-shadow: 0 0 5px #00ccff, 0 0 25px #00ccff, 0 0 50px #00ccff, 0 0 200px #00ccff;
    border-radius: 5px;
    transition: 0.5s;
    transition-delay: 0s;
}

.glassmorphism-btn:hover::before {
    bottom: 0;
    height: 40%;
    width: 95%;
    border-radius: 50px;
    transition-delay: 0.5s;
}

.glassmorphism-btn::after {
    content: '';
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    top: -5px;
    width: 50px;
    height: 10px;
    background: #00ccff;
    box-shadow: 0 0 5px #00ccff, 0 0 25px #00ccff, 0 0 50px #00ccff, 0 0 200px #00ccff;
    border-radius: 5px;
    transition: 0.5s;
    transition-delay: 0s;
}

.glassmorphism-btn:hover::after {
    top: 0;
    height: 50%;
    width: 95%;
    border-radius: 50px;
    transition-delay: 0.5s;
}

.glassmorphism-btn:first-child:before,
.glassmorphism-btn:first-child:after {
    background: #1eff00;
    box-shadow: 0 0 5px #1eff00, 0 0 25px #1eff00, 0 0 50px #1eff00, 0 0 200px #1eff00;
}


</style>