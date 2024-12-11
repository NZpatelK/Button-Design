<template>
    <div class="dark-switch-container">
        <label>
            <input type="checkbox">
            <span></span>
            <i class="indicator on">i</i>
            <i class="indicator off">o</i>
        </label>
    </div>
</template>

<style>
.dark-switch-container {
    display: flex;
    justify-content: center;
    align-items: center;
    background: #444;
    height: 100vh;
    width: 100vw;
}

.dark-switch-container label {
    position: relative;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin-bottom: 100px;
}

.dark-switch-container label input {
    appearance: none;
    display: none;
}

.dark-switch-container label span {
  position: relative;
    display: block;
    width: 160px;
    height: 360px;
    border: 4px solid #111; 
    border-radius: 10px;
    box-shadow: inset 0 2px 20px rgba(0, 0, 0, 0.9);
}

.dark-switch-container label span::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%; 
    height: calc(100% - 25px);
    background: linear-gradient(#444 0%, #444 50%, #444, #151515 100%);
    border-radius: 10px;
}

.dark-switch-container label input:checked ~ span::before {
    top: 25px;
    background: linear-gradient(#151515 0%, #444 50%, #444, #444 100%);
}

.dark-switch-container label i {
    position: absolute;
    color: #111;
    text-transform: uppercase;
    font-style: initial;
    font-size: 700;
    font-size: 5rem;
}

.dark-switch-container label i.off {
    bottom: 40px;
    color: #f00;
    text-shadow: 0 0 5px #f00,
    0 0 15px #f00;
}

.dark-switch-container input:checked ~  i.off {
    bottom: 20px;
    color: #111;
    text-shadow: none;
}

.dark-switch-container label i.on {
    top: 20px;
    color: #111;
    text-shadow: none;
}

.dark-switch-container input:checked ~ i.on {
    top: 40px;
    color: #0f0;
    text-shadow: 0 0 5px #0f0,
    0 0 15px #0f0;
}




</style>