<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Crisantemo Animado</title>
<style>
    body {
        margin: 0;
        background: #ffe6f2;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        overflow: hidden;
        font-family: Arial, sans-serif;
    }

    header {
        font-family: "Comic Sans MS", cursive;
        font-size: 6rem;
        color: #ff1493;
        opacity: 0;
        text-shadow: 0 0 20px #ff5fa2;
        transition: opacity 2s ease-in-out;
    }

    #mensaje2 {
        font-family: "Comic Sans MS", cursive;
        font-size: 4rem;
        color: #ff007f;
        opacity: 0;
        margin-top: 20px;
        transition: opacity 1s ease-in-out;
        text-shadow: 0 0 15px #ff5fa2;
    }

    .flower {
        width: 260px;
        height: 260px;
        position: relative;
        animation: bloom 4s ease forwards;
        transform: scale(0);
        cursor: pointer;
    }

    @keyframes bloom {
        0% { transform: scale(0); }
        60% { transform: scale(1.2); }
        100% { transform: scale(1); }
    }

    .petal {
        width: 70px;
        height: 150px;
        background: radial-gradient(circle at 30% 30%, #ff9acb, #ff61b0, #ff2f92);
        border-radius: 60% 60% 0 0;
        position: absolute;
        left: 50%;
        top: 50%;
        transform-origin: bottom center;
        filter: drop-shadow(0 0 6px #ff8ac8);
    }

    .center {
        width: 80px;
        height: 80px;
        background: #ffcf33;
        border-radius: 50%;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        box-shadow: 0 0 15px #ffb300;
        cursor: pointer;
    }
</style>
</head>
<body>

<header id="mensaje"></header>
<div id="mensaje2"></div>

<div class="flower" id="flor"></div>

<script>
// Crear pétalos
const flower = document.getElementById("flor");
const petalCount = 32;

for (let i = 0; i < petalCount; i++) {
    const petal = document.createElement("div");
    petal.classList.add("petal");
    petal.style.transform = `translate(-50%, -100%) rotate(${(360 / petalCount) * i}deg)`;
    flower.appendChild(petal);
}

// Crear centro
const center = document.createElement("div");
center.classList.add("center");
flower.appendChild(center);

// Mostrar "Te amo"
setTimeout(() => {
    const header = document.getElementById("mensaje");
    header.textContent = "Te amo";
    header.style.opacity = 1;
}, 4000);

// Mensaje al tocar el centro
center.addEventListener("click", () => {
    const msg2 = document.getElementById("mensaje2");
    msg2.textContent = "Eres muy lindo";
    msg2.style.opacity = 1;
});
</script>

</body>
</html>
