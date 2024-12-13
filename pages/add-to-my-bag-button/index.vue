<template>
    <div class="add-my-bag-btn-container">
        <button class="button btn-cart">
            <span>
                <span>
                    Add to My Bag
                </span>
            </span>
        </button>
    </div>
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
:root {
    --button-color: #c98702;
    --time: 400ms;
    --bag-height: 20px;
}


.add-my-bag-btn-container {
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    height: 100vh;
    width: 100vw;
    background: #333;
}

.btn-cart {
    display: block;
    width: 200px;
    line-height: 44px;
    border: none;
    margin: 0 auto;
    background: none;
    text-transform: uppercase;
    color: #fff;
    letter-spacing: 1px;
    font-size: 18px;
    font-family: 'Poppins', sans-serif;
    font-weight: 500;
    position: relative;
    cursor: pointer;}


.btn-cart:before {
    content: "";
    display: block;
    width: calc(var(--bag-height) * 0.6);
    height: calc(var(--bag-height) * 0.6);
    position: absolute;
    border: 2px solid var(--button-color);
    transform: translateX(0);
    left: 94px;
    border-radius: 50%;
    top: 5px;
    box-sizing: border-box;
}

.btn-cart:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: var(--button-color);
    border-radius: 10px;
    transition: all var(--time) cubic-bezier(0.175, 0.885, 0.32, 1.275);
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.2);

}

.btn-cart:focus {
    outline: none;
}

.btn-cart:focus:before {
    animation: shift-left-circle calc(var(--time) * 2) forwards;
    animation-delay: calc(var(--time) * 3);
}

.btn-cart:focus:after {
    width: 20px;
    height: 20px;
    top: 12px;
    left: 90px;
    border-radius: 0;
    animation: shift-left var(--time) forwards;
    animation-delay: calc(var(--time) * 3);
    transition-delay: var(--time);
}

.btn-cart:focus>span {
    position: relative;
    display: block;
}

.btn-cart:focus>span:before {
    content: "";
    display: block;
    position: absolute;
    width: 12px;
    height: 20px;
    background: #333;
    top: 5px;
    left: 94px;
    animation-timing-function: linear;
    transform: translateX(0) rotate(0deg);
    transform-origin: center bottom;
    animation: shift-left-mask calc(var(--time) * 2) forwards;
    animation-delay: calc(var(--time) * 2);
}

.btn-cart:focus>span:after {
    content: "ADDED";
    color: rgb(1, 210, 1);
    position: absolute;
    z-index: 100;
    left: 50%;
    opacity: 0;
    transition: all var(--time) cubic-bezier(0.175, 0.885, 0.32, 1.275);
    transform: translate(-30%, 20px);
    animation: added-label-lift var(--time) forwards calc(var(--time) * 4);
}

.btn-cart span span {
    display: inline-block;
    position: relative;
    z-index: 2;
    transition: all var(--time) cubic-bezier(0.175, 0.885, 0.32, 1.275);
    transform: translateY(0px);
}

.btn-cart:focus span span {
    opacity: 0;
    transform: translateY(20px);
}

@keyframes shift-left {
    0% {
        transform: translateX(0);
    }

    100% {
        transform: translateX(-40px);
    }
}

@keyframes shift-left-circle {
    0% {
        transform: translateX(0);
    }

    50% {
        transform: translateX(-40px);
    }

    100% {
        transform: translateX(-40px);
    }
}

@keyframes shift-left-mask {
    0% {
        height: 7px;
        transform: translateX(0) rotate(0);
    }

    50% {
        transform: translateX(0) rotate(180deg);
    }

    100% {
        transform: translateX(-40px) rotate(180deg);
    }
}

@keyframes added-label-lift{
    0%{
        opacity: 0;
        transform: translate(-30%, 20px);
    }
    100%{
        opacity: 1;
        transform: translate(-30%, 0);
    }
}
</style>