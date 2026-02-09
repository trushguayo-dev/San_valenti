#San_valenti
Página para romi
<!DOCTYPE html><html lang="es">
<head>
<meta charset="UTF-8">
<title>Romina, ¿quieres ser mi San Valentín?</title>
<style>
    body {
        font-family: 'Arial', sans-serif;
        background: linear-gradient(135deg, #a0c4ff, #4d79ff);
        color: #f0f0f0;
        text-align: center;
        padding-top: 50px;
        height: 100vh;
        overflow: hidden;
        transition: background 1s;
    }
    h1 {
        font-size: 3rem;
        color: #1e90ff;
        margin-bottom: 10px;
        text-shadow: 2px 2px #00000050;
    }
    p {
        font-size: 1.3rem;
        margin-bottom: 30px;
        color: #e0f7ff;
        text-shadow: 1px 1px #00000050;
    }
    .fecha {
        font-size: 1rem;
        color: #cce7ff;
        margin-bottom: 40px;
    }
    button {
        background-color: #ffffff;
        color: #1e90ff;
        padding: 15px 35px;
        border: none;
        font-size: 1.3rem;
        border-radius: 15px;
        cursor: pointer;
        margin: 10px;
        transition: 0.3s;
        box-shadow: 2px 2px 10px #00000050;
    }
    button:hover {
        transform: scale(1.1);
    }
    #noBtn {
        background-color: #cce7ff;
        color: #004080;
    }
    .corazon, .gatito {
        position: absolute;
        animation: flotar 5s infinite ease-in-out;
        opacity: 0.8;
    }
    .gatito {
        font-size: 25px;
    }
    @keyframes flotar {
        0% { transform: translateY(0); opacity: 0.7; }
        50% { transform: translateY(-50px); opacity: 1; }
        100% { transform: translateY(0); opacity: 0.7; }
    }
    .mensaje-si {
        display: none;
        font-size: 1.5rem;
        color: #00ffea;
        margin-top: 30px;
        animation: aparecer 1s forwards;
    }
    @keyframes aparecer {
        from { opacity: 0; transform: scale(0.5); }
        to { opacity: 1; transform: scale(1); }
    }
    .fondo-si {
        display: none;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(135deg, #ffb3ff, #ff4dff);
        z-index: -1;
    }
    audio {
        display: none;
    }
</style>
</head>
<body><h1>Romina, ¿quieres ser mi San Valentín? 💙</h1>
<p>Desde que empezamos a hablar el <span class="fecha">12/01/26</span>, cada día pienso en ti 😍</p><button id="siBtn">Sí</button> <button id="noBtn">No</button>

<div class="mensaje-si" id="mensajeSi">
  ¡Sabía que dirías que sí! 💙<br>Estoy muy feliz de que podamos compartir momentos juntos 😻💫
</div>
<div class="fondo-si" id="fondoSi"></div><iframe width="320" height="180"
    src="https://www.youtube.com/embed/8obld3JrBNM?autoplay=1&loop=1&playlist=8obld3JrBNM"
    title="YouTube video player"
    frameborder="0"
    allow="autoplay; encrypted-media"
    allowfullscreen>
</iframe><script>
    const noBtn = document.getElementById("noBtn");
    const siBtn = document.getElementById("siBtn");
    const mensajeSi = document.getElementById("mensajeSi");
    const fondoSi = document.getElementById("fondoSi");

    // Acción para NO
    noBtn.addEventListener("click", () => {
        noBtn.style.transition = "opacity 1s";
        noBtn.style.opacity = 0;
        noBtn.style.pointerEvents = 'none';
        const aviso = document.createElement('p');
        aviso.innerText = 'Ups… todavía tienes tiempo de pensarlo 😻💙';
        aviso.style.color = '#cce7ff';
        aviso.style.fontSize = '1.2rem';
        document.body.appendChild(aviso);
        setTimeout(() => { aviso.remove(); }, 4000);
    });

    // Acción para SÍ - nueva sección mágica
    siBtn.addEventListener("click", () => {
        siBtn.style.display = 'none';
        noBtn.style.display = 'none';
        mensajeSi.style.display = 'block';
        fondoSi.style.display = 'block';

        // Corazones que explotan al centro
        for(let i=0; i<30; i++){
            const corazon = document.createElement('div');
            corazon.classList.add('corazon');
            corazon.innerHTML = '💙';
            corazon.style.left = (window.innerWidth/2 + Math.random()*200 - 100) + 'px';
            corazon.style.top = (window.innerHeight/2 + Math.random()*200 - 100) + 'px';
            corazon.style.fontSize = (30 + Math.random()*40) + 'px';
            document.body.appendChild(corazon);
            setTimeout(() => { corazon.remove(); }, 4000);
        }
    });

    // Corazones y gatitos flotando constantemente
    function crearCorazon() {
        const corazon = document.createElement("div");
        corazon.classList.add("corazon");
        corazon.innerHTML = "💙";
        corazon.style.left = Math.random() * window.innerWidth + "px";
        corazon.style.top = Math.random() * window.innerHeight + "px";
        corazon.style.fontSize = (20 + Math.random() * 40) + "px";
        document.body.appendChild(corazon);
        setTimeout(() => { corazon.remove(); }, 5000);
    }

    function crearGatito() {
        const gatito = document.createElement("div");
        gatito.classList.add("gatito");
        gatito.innerHTML = "😻";
        gatito.style.left = Math.random() * window.innerWidth + "px";
        gatito.style.top = Math.random() * window.innerHeight + "px";
        document.body.appendChild(gatito);
        setTimeout(() => { gatito.remove(); }, 5000);
    }

    setInterval(crearCorazon, 700);
    setInterval(crearGatito, 1200);
</script></body>
</html>