<template>
    <div class="booking-button-container">
        <button class="book-btn">
            <span>
                <span class="book-btn-container">
                    <span class="primary"></span>
                    <span class="complimentary"></span>
                </span>
            </span>
            <span>Book a demo</span>
        </button>
    </div>
</template>

<style>
@import 'normalize.css';
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');


.booking-button-container{
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    height: 100vh;
    width: 100vw;
}

.book-btn {
    height: 48px;
    padding: 0;
    display: grid;
    border-radius: 8px;
    border: 2px solid black;
    letter-spacing: 0.25px;
    cursor: pointer;
    position: relative;
    background: black;
    color: white;
    font-family: 'Poppins', sans-serif;
    font-weight: 300;
    text-transform: capitalize;
    scale: 2;
    outline-color: #00bfe6;
    outline-offset: 0.25rem;
    box-shadow: 0 5px 10px -5px rgba(0, 0, 0, 0.5);
}

.book-btn:is(:hover, :focus-visible) {
    --active: 1;
}

.book-btn:active {
    --pressed: 1;
}

.book-btn>span:nth-of-type(1) {
    height: 100%;
    width: 100%;
    border-radius: 8px;
    position: absolute;
    inset: 0;
    scale: calc(1 - (var(--pressed, 0) * 0.05));
    transition: scale 0.1s;
}

.book-btn:is(:hover, :focus-visible) .book-btn-container {
    width: 100%;
}

.book-btn-container {
    --mask-image: url(../../assets/chev-mask.webp);
    --spread: 24px;
    --size: 28px;
    width: 58px;
    height: 100%;
    background: #00bfe6;
    position: absolute;
    left: 0;
    transition: width 0.25s;
    border-radius: 6px;
    box-shadow: 0 10px 10px -5px hsl(0 0% 0% / 0.5);
    book-btn-container-type: inline-size;
}

.primary {
    content: "";
    position: absolute;
    inset: 0;
    background: hsl(0 0% 0% / 0.15);
    z-index: 2;
    -webkit-mask: var(--mask-image) 50% 50% / var(--size) var(--size) no-repeat;
    mask: var(--mask-image) 50% 50% / var(--size) var(--size) no-repeat;
    book-btn-container-type: inline-size;
}

:where(.primary, .complimentary)::after {
    --distance: calc(100cqi + 100%);
    content: "";
    height: calc(var(--size) * 4);
    aspect-ratio: 1;
    position: absolute;
    left: 0%;
    top: 50%;
    translate: -50% -50%;
    background: radial-gradient(hsl(0 0% 0%), transparent);
    -webkit-animation: fly-by calc((2 - var(--active, 0)) * 1s) infinite linear;
    animation: fly-by calc((2 - var(--active, 0)) * 1s) infinite linear;
}

@-webkit-keyframes fly-by {
    0% {
        translate: -100% -50%;
    }

    100% {
        translate: var(--distance) -50%;
    }
}

@keyframes fly-by {
    0% {
        translate: -100% -50%;
    }

    100% {
        translate: var(--distance) -50%;
    }
}

.complimentary {
    content: "";
    position: absolute;
    inset: 0;
    opacity: var(--active, 0);
    transition: opacity 0.25s;
    background: hsl(0 0% 0% / 0.15);
    -webkit-mask:
        var(--mask-image) calc(50% - (var(--spread) * 1)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% - (var(--spread) * 2)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% - (var(--spread) * 3)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% + (var(--spread) * 1)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% + (var(--spread) * 2)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% + (var(--spread) * 3)) 50% / var(--size) var(--size) no-repeat;
    mask:
        var(--mask-image) calc(50% - (var(--spread) * 1)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% - (var(--spread) * 2)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% - (var(--spread) * 3)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% + (var(--spread) * 1)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% + (var(--spread) * 2)) 50% / var(--size) var(--size) no-repeat,
        var(--mask-image) calc(50% + (var(--spread) * 3)) 50% / var(--size) var(--size) no-repeat;
}

button>span:nth-of-type(2) {
    padding: 0 1.1rem 0 calc(58px + 1.1rem);
    display: grid;
    place-items: center;
    height: 100%;
}
</style>