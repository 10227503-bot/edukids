<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduKids - Portal de Aprendizaje Infinito</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@400;700&family=Afacad+Flux:wght@400;600;700&display=swap" rel="stylesheet">

    <style>
        /* 1. VARIABLES DE DISEÑO Y CONFIGURACIÓN BÁSICA */
        :root {
            --naranja: #FF823A;
            --morado: #BC84EE;
            --verde-lima: #DCFD8B;
            --azul-oscuro: #1E293B;
            --gris-suave: #F8FAFC;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Afacad Flux', sans-serif;
            background-color: #F1F5F9;
            color: var(--azul-oscuro);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        /* 2. HEADER COMPACTO Y RESPONSIVO */
        header {
            background-color: #FFFFFF;
            padding: 15px 30px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .edukids-logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-family: 'Comfortaa', cursive;
            text-decoration: none;
            user-select: none;
        }

        .logo-text-edu { color: var(--naranja); font-size: 32px; font-weight: 700; }
        .logo-text-kids { color: var(--morado); font-size: 32px; font-weight: 700; }

        .logo-icon { transition: transform 0.3s ease, filter 0.3s ease; }
        .edukids-logo:hover .logo-icon {
            transform: scale(1.1) rotate(-5deg);
            filter: drop-shadow(0 0 8px var(--verde-lima));
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 12px;
        }

        nav a {
            text-decoration: none;
            color: var(--azul-oscuro);
            font-size: 15px;
            font-weight: 600;
            font-family: 'Comfortaa', cursive;
            transition: all 0.2s;
            cursor: pointer;
            padding: 5px 10px;
            border-radius: 10px;
        }

        nav a:hover, nav a.active {
            color: white;
            background-color: var(--morado);
        }

        /* 3. ZONA CENTRAL DE JUEGOS */
        main {
            flex-grow: 1;
            max-width: 1200px;
            width: 100%;
            margin: 30px auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .welcome-section h1 {
            font-family: 'Comfortaa', cursive;
            font-size: 46px;
            color: var(--azul-oscuro);
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .welcome-section h1 span { color: var(--naranja); }
        .welcome-section p { font-size: 22px; color: #475569; line-height: 1.5; margin-bottom: 30px; }

        /* Contenedor Principal del Juego */
        .game-card {
            background-color: #FFFFFF;
            border: 8px solid var(--naranja);
            border-radius: 40px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 20px 40px rgba(0,0,0,0.05);
            transition: border-color 0.3s ease;
        }

        .game-card h2 {
            font-family: 'Comfortaa', cursive;
            font-size: 26px;
            margin-bottom: 5px;
            color: var(--azul-oscuro);
        }

        /* Estilos de la Barra de Progreso Avanzada */
        .level-status {
            font-size: 18px;
            font-weight: bold;
            color: var(--azul-oscuro);
            margin-bottom: 12px;
            display: flex;
            justify-content: space-between;
            padding: 0 5px;
        }

        .progress-container {
            background-color: #E2E8F0;
            border-radius: 20px;
            height: 18px;
            width: 100%;
            margin-bottom: 25px;
            overflow: hidden;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.08);
            border: 2px solid #E2E8F0;
            display: none;
        }

        .progress-bar {
            background: linear-gradient(90deg, #A855F7, #6EE7B7);
            height: 100%;
            width: 0%;
            transition: width 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            border-radius: 20px;
        }

        /* Pantalla de Despliegue de Desafíos */
        .game-display {
            font-family: 'Comfortaa', cursive;
            font-size: 28px;
            min-height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            color: var(--azul-oscuro);
            background-color: var(--gris-suave);
            padding: 20px;
            border-radius: 20px;
            line-height: 1.4;
        }

        /* Lienzo Especial del Módulo de Artes */
        #art-canvas {
            background-color: #FFFFFF;
            border: 3px dashed #CBD5E1;
            border-radius: 15px;
            cursor: crosshair;
            display: none;
        }

        .options-grid {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 20px;
        }

        /* Herramientas de la Paleta de Pintura */
        .color-palette {
            display: none;
            justify-content: center;
            gap: 10px;
            margin-bottom: 15px;
        }

        .color-circle {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            cursor: pointer;
            border: 3px solid transparent;
        }

        .color-circle.active { border-color: var(--azul-oscuro); transform: scale(1.1); }

        /* Botones del Sistema de Trivia */
        .game-btn {
            background-color: var(--morado);
            color: white;
            border: none;
            padding: 14px 25px;
            font-size: 18px;
            font-family: 'Comfortaa', cursive;
            border-radius: 20px;
            cursor: pointer;
            transition: transform 0.1s, background-color 0.2s;
            box-shadow: 0 6px 0 #9333EA;
            width: 100%;
        }

        .game-btn:hover { transform: translateY(-2px); background-color: #A855F7; }
        .game-btn:active { transform: translateY(4px); box-shadow: none; }

        .score-board { font-size: 22px; font-weight: 700; color: #64748B; margin-top: 15px;}
        .score-board span { color: var(--naranja); font-size: 26px; }

        .reset-btn {
            background: none;
            border: none;
            color: #94A3B8;
            font-size: 13px;
            cursor: pointer;
            text-decoration: underline;
            margin-top: 15px;
        }
        .reset-btn:hover { color: #64748B; }

        /* 4. PIE DE PÁGINA */
        footer {
            background-color: var(--azul-oscuro);
            color: white;
            text-align: center;
            padding: 20px;
            font-size: 16px;
            margin-top: auto;
        }
    </style>
</head>
<body>

    <header>
        <a href="#" class="edukids-logo" onclick="cargarSeccion('inicio')">
            <svg class="logo-icon" width="45" height="45" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="50" cy="42" r="30" fill="#DCFD8B" opacity="0.4"/>
                <path d="M50 15C33.5 15 20 28.5 20 45C20 56 26 65.5 35 70.5V78C35 81 37.5 83.5 40.5 83.5H59.5C62.5 83.5 65 81 65 78V70.5C74 65.5 80 56 80 45C80 28.5 66.5 15 50 15Z" fill="#BC84EE"/>
                <path d="M40 45C40 39.5 44.5 35 50 35C55.5 35 60 45 50 55C46 51 40 50.5 40 45Z" fill="#DCFD8B"/>
                <path d="M38 78H62V82C62 84 60.5 85 58.5 85H41.5C39.5 85 38 84 38 82V78Z" fill="#94A3B8"/>
                <line x1="42" y1="81" x2="58" y2="81" stroke="#64748B" stroke-width="2" stroke-linecap="round"/>
                <line x1="50" y1="5" x2="50" y2="10" stroke="#FF823A" stroke-width="4" stroke-linecap="round"/>
            </svg>
            <div class="logo-text"><span class="logo-text-edu">Edu</span><span class="logo-text-kids">Kids</span></div>
        </a>
        <nav>
            <ul>
                <li><a id="btn-inicio" class="active" onclick="cargarSeccion('inicio')">Inicio</a></li>
                <li><a id="btn-math" onclick="cargarSeccion('math')">Matemáticas</a></li>
                <li><a id="btn-ciencia" onclick="cargarSeccion('ciencia')">Ciencias</a></li>
                <li><a id="btn-lenguaje" onclick="cargarSeccion('lenguaje')">Lenguaje</a></li>
                <li><a id="btn-sociales" onclick="cargarSeccion('sociales')">Sociales</a></li>
                <li><a id="btn-ingles" onclick="cargarSeccion('ingles')">Inglés</a></li>
                <li><a id="btn-artes" onclick="cargarSeccion('artes')">Artes</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <div class="welcome-section">
            <h1 id="main-title">¡Aprender es una gran <span>Aventura</span>!</h1>
            <p id="main-desc">Resuelve misiones interactivas a lo largo de 100 niveles de dificultad. ¡Tu progreso se guarda automáticamente!</p>
        </div>

        <div class="game-card" id="game-card">
            <div class="level-status" id="level-status"><span>Materia no seleccionada</span><span id="percentage-txt"></span></div>
            <div class="progress-container" id="progress-container"><div class="progress-bar" id="progress-bar"></div></div>
            
            <h2 id="game-title">¿Listo para el reto de los 100 niveles?</h2>
            
            <div class="game-display" id="game-display">
                <span id="text-prompt">Elige una materia en el menú de arriba para iniciar tu viaje.</span>
                <canvas id="art-canvas" width="340" height="180"></canvas>
            </div>

            <div class="color-palette" id="color-palette">
                <div class="color-circle active" style="background-color: #FF823A;" onclick="cambiarColor('#FF823A', this)"></div>
                <div class="color-circle" style="background-color: #BC84EE;" onclick="cambiarColor('#BC84EE', this)"></div>
                <div class="color-circle" style="background-color: #00D2C4;" onclick="cambiarColor('#00D2C4', this)"></div>
                <div class="color-circle" style="background-color: #1E293B;" onclick="cambiarColor('#1E293B', this)"></div>
            </div>

            <div class="options-grid" id="options-container">
                <button class="game-btn" style="background-color: var(--naranja); box-shadow: 0 6px 0 #C2410C;" onclick="cargarSeccion('math')">¡Empezar con Matemáticas!</button>
            </div>
            
            <div class="score-board">Estrellas Totales: <span id="score-val">0</span> ⭐</div>
            <button class="reset-btn" onclick="reiniciarTodoElProgreso()">Reiniciar juego desde cero</button>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 EduKids - Portal de Aprendizaje Infinito.</p>
    </footer>

    <script>
        let estrellasTotales = 0;
        let seccionActual = "inicio";
        let respuestaCorrectaActual = "";
        let nivelesMaterias = { math: 1, ciencia: 1, lenguaje: 1, sociales: 1, ingles: 1, artes: 1 };

        // MECÁNICAS E INSTANCIAS DE CANVAS (ARTE)
        const canvas = document.getElementById('art-canvas');
        const ctx = canvas.getContext('2d');
        let dibujando = false; let colorPincel = '#FF823A';

        canvas.addEventListener('mousedown', () => dibujando = true);
        canvas.addEventListener('mouseup', () => { dibujando = false; ctx.beginPath(); });
        canvas.addEventListener('mousemove', (e) => {
            if(!dibujando) return;
            const rect = canvas.getBoundingClientRect();
            ctx.lineWidth = 5; ctx.lineCap = 'round'; ctx.strokeStyle = colorPincel;
            ctx.lineTo(e.clientX - rect.left, e.clientY - rect.top); ctx.stroke();
            ctx.beginPath(); ctx.moveTo(e.clientX - rect.left, e.clientY - rect.top);
        });

        // Eventos táctiles para dispositivos móviles
        canvas.addEventListener('touchstart', (e) => { dibujando = true; e.preventDefault(); });
        canvas.addEventListener('touchend', () => { dibujando = false; ctx.beginPath(); });
        canvas.addEventListener('touchmove', (e) => {
            if(!dibujando) return;
            const touch = e.touches[0];
            const rect = canvas.getBoundingClientRect();
            ctx.lineWidth = 5; ctx.lineCap = 'round'; ctx.strokeStyle = colorPincel;
            ctx.lineTo(touch.clientX - rect.left, touch.clientY - rect.top); ctx.stroke();
            ctx.beginPath(); ctx.moveTo(touch.clientX - rect.left, touch.clientY - rect.top);
        });

        function cambiarColor(color, elemento) {
            colorPincel = color;
            document.querySelectorAll('.color-circle').forEach(c => c.classList.remove('active'));
            elemento.classList.add('active');
        }

        // CONTROLADORES DE ALMACENAMIENTO (AUTO-GUARDADO LOCAL)
        function guardarProgreso() {
            localStorage.setItem('eduKids_niveles', JSON.stringify(nivelesMaterias));
            localStorage.setItem('eduKids_estrellas', estrellasTotales);
        }

        function cargarProgresoGuardado() {
            const nivelesGuardados = localStorage.getItem('eduKids_niveles');
            const estrellasGuardadas = localStorage.getItem('eduKids_estrellas');
            
            if (nivelesGuardados) { nivelesMaterias = JSON.parse(nivelesGuardados); }
            if (estrellasGuardadas) {
                estrellasTotales = parseInt(estrellasGuardadas);
                document.getElementById('score-val').innerText = estrellasTotales;
            }
        }

        function reiniciarTodoElProgreso() {
            if (confirm("¿Seguro que quieres borrar todas tus estrellas y volver al Nivel 1?")) {
                nivelesMaterias = { math: 1, ciencia: 1, lenguaje: 1, sociales: 1, ingles: 1, artes: 1 };
                estrellasTotales = 0;
                guardarProgreso();
                document.getElementById('score-val').innerText = estrellasTotales;
                cargarSeccion('inicio');
            }
        }

        // GESTIÓN DE INTERFAZ DINÁMICA
        function cargarSeccion(seccion) {
            seccionActual = seccion;
            canvas.style.display = 'none';
            document.getElementById('color-palette').style.display = 'none';
            document.getElementById('text-prompt').style.display = 'block';
            document.getElementById('progress-container').style.display = seccion === 'inicio' ? 'none' : 'block';

            document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
            document.getElementById('btn-' + seccion).classList.add('active');
            
            const tarjeta = document.getElementById('game-card');

            if(seccion === 'inicio') {
                document.getElementById('level-status').innerHTML = "<span>Materia no seleccionada</span>";
                document.getElementById('main-title').innerHTML = "¡Aprender es una gran <span>Aventura</span>!";
                document.getElementById('game-title').innerText = "¿Listo para el reto de los 100 niveles?";
                document.getElementById('text-prompt').innerText = "Elige una materia en el menú de arriba para iniciar tu viaje.";
                tarjeta.style.borderColor = "var(--naranja)";
                document.getElementById('options-container').innerHTML = `<button class="game-btn" style="background-color: var(--naranja); box-shadow: 0 6px 0 #C2410C;" onclick="cargarSeccion('math')">¡Empezar con Matemáticas!</button>`;
            } else {
                actualizarBarraProgreso();
                ejecutarMotorJuego();
            }
        }

        function actualizarBarraProgreso() {
            let nivelActual = nivelesMaterias[seccionActual];
            let nombresMaterias = {math: "Matemáticas", ciencia: "Ciencias", lenguaje: "Lenguaje", sociales: "Sociales", ingles: "Inglés", artes: "Artes"};
            document.getElementById('level-status').innerHTML = `<span>Materia: ${nombresMaterias[seccionActual]}</span> <span>Nivel ${nivelActual}/100</span>`;
            document.getElementById('progress-bar').style.width = `${nivelActual}%`;
        }

        // MOTOR CENTRAL ALGORÍTMICO GENERADOR DE DESAFÍOS
        function ejecutarMotorJuego() {
            const lvl = nivelesMaterias[seccionActual];
            const tarjeta = document.getElementById('game-card');
            
            if(['ciencia', 'sociales', 'artes'].includes(seccionActual)) {
                tarjeta.style.borderColor = "var(--morado)";
            } else {
                tarjeta.style.borderColor = "var(--naranja)";
            }

            if(seccionActual === 'math') {
                document.getElementById('game-title').innerText = "Cálculo Mental";
                let num1 = Math.floor(Math.random() * (lvl + 5)) + 1;
                let num2 = Math.floor(Math.random() * (lvl + 5)) + 1;
                let operacion = lvl > 25 && Math.random() > 0.5 ? '-' : '+';
                
                if(operacion === '-') {
                    if(num1 < num2) { let t = num1; num1 = num2; num2 = t; }
                    respuestaCorrectaActual = (num1 - num2).toString();
                } else {
                    respuestaCorrectaActual = (num1 + num2).toString();
                }
                
                document.getElementById('text-prompt').innerText = `¿Cuánto es ${num1} ${operacion} ${num2}?`;
                let c = parseInt(respuestaCorrectaActual);
                renderizarBotones([c, c + 3, c - 2].sort(() => Math.random() - 0.5));
            }
            
            else if(seccionActual === 'ciencia') {
                document.getElementById('game-title').innerText = "Trivia Ciencias";
                let banco = [
                    {q: "¿Cuál es el planeta más cercano al Sol?", a: "Mercurio", o: ["Marte", "Venus"]},
                    {q: "¿Qué estrella calienta nuestro planeta?", a: "El Sol", o: ["Sirio", "Orión"]},
                    {q: "¿Qué estado del agua es el hielo?", a: "Sólido", o: ["Líquido", "Gaseoso"]}
                ];
                let item = banco[(lvl + Math.floor(Math.random()*3)) % banco.length];
                respuestaCorrectaActual = item.a;
                document.getElementById('text-prompt').innerText = item.q;
                renderizarBotones([item.a, ...item.o].sort(() => Math.random() - 0.5));
            }

            else if(seccionActual === 'lenguaje') {
                document.getElementById('game-title').innerText = "Ortografía Súper";
                let banco = [
                    {q: "La palabra co__er se escribe con:", a: "m (comer)", o: ["n (coner)"]},
                    {q: "El animal ca__allo se escribe con:", a: "b (caballo)", o: ["v (cavallo)"]},
                    {q: "Completa: Hoy voy a __isitar a mi abuelo.", a: "v (visitar)", o: ["b (bisitar)"]}
                ];
                let item = banco[(lvl + Math.floor(Math.random()*3)) % banco.length];
                respuestaCorrectaActual = item.a;
                document.getElementById('text-prompt').innerText = item.q;
                renderizarBotones([item.a, ...item.o].sort(() => Math.random() - 0.5));
            }

            else if(seccionActual === 'sociales') {
                document.getElementById('game-title').innerText = "Geomapas";
                let banco = [
                    {q: "¿En qué planeta se encuentra el continente Americano?", a: "La Tierra", o: ["Marte", "Júpiter"]},
                    {q: "¿Qué aguja magnética señala el Norte?", a: "La brújula", o: ["El reloj", "El termómetro"]},
                    {q: "¿Cuántos océanos principales tiene la Tierra?", a: "5", o: ["3", "7"]}
                ];
                let item = banco[(lvl + Math.floor(Math.random()*3)) % banco.length];
                respuestaCorrectaActual = item.a;
                document.getElementById('text-prompt').innerText = item.q;
                renderizarBotones([item.a, ...item.o].sort(() => Math.random() - 0.5));
            }

            else if(seccionActual === 'ingles') {
                document.getElementById('game-title').innerText = "English Challenge";
                let banco = [
                    {q: "¿Cómo se traduce 'Manzana'?", a: "Apple", o: ["Banana", "Grape"]},
                    {q: "¿Qué significa el color 'Yellow'?", a: "Amarillo", o: ["Azul", "Rojo"]},
                    {q: "¿Cómo saludas por la mañana?", a: "Good morning", o: ["Good night", "Goodbye"]}
                ];
                let item = banco[(lvl + Math.floor(Math.random()*3)) % banco.length];
                respuestaCorrectaActual = item.a;
                document.getElementById('text-prompt').innerText = item.q;
                renderizarBotones([item.a, ...item.o].sort(() => Math.random() - 0.5));
            }

            else if(seccionActual === 'artes') {
                canvas.style.display = 'block';
                document.getElementById('color-palette').style.display = 'flex';
                document.getElementById('text-prompt').style.display = 'none';
                ctx.clearRect(0, 0, canvas.width, canvas.height);

                let dibujos = ["un cohete espacial", "un gato feliz", "un árbol mágico", "un dinosaurio", "un helado gigante", "un alien divertido"];
                let objetivo = dibujos[(lvl + Math.floor(Math.random()*3)) % dibujos.length];
                document.getElementById('game-title').innerText = `Reto: Dibuja ${objetivo}`;
                
                document.getElementById('options-container').innerHTML = `<button class="game-btn" style="background-color: var(--verde-lima); color: var(--azul-oscuro); box-shadow: 0 6px 0 #A3E635;" onclick="procesarRespuestaArtes()">¡Guardar Dibujo y Subir Nivel! ⭐</button>`;
            }
        }

        function renderizarBotones(lista) {
            const contenedor = document.getElementById('options-container');
            contenedor.innerHTML = '';
            lista.forEach(opcion => {
                const boton = document.createElement('button');
                boton.className = 'game-btn';
                if(['ciencia', 'sociales', 'ingles'].includes(seccionActual)) {
                    boton.style.backgroundColor = "var(--morado)";
                    boton.style.boxShadow = "0 6px 0 #7C3AED";
                } else {
                    boton.style.backgroundColor = "var(--naranja)";
                    boton.style.boxShadow = "0 6px 0 #C2410C";
                }
                boton.innerText = opcion;
                boton.onclick = () => verificarRespuesta(opcion.toString());
                contenedor.appendChild(boton);
            });
        }

        function verificarRespuesta(seleccionada) {
            const tarjeta = document.getElementById('game-card');
            if(seleccionada === respuestaCorrectaActual) {
                estrellasTotales += 1;
                tarjeta.style.borderColor = "var(--verde-lima)";
                
                if(nivelesMaterias[seccionActual] < 100) { nivelesMaterias[seccionActual] += 1; }
                guardarProgreso();

                setTimeout(() => {
                    restaurarBordesCard();
                    actualizarBarraProgreso();
                    ejecutarMotorJuego();
                }, 500);
            } else {
                tarjeta.style.borderColor = "#EF4444";
                setTimeout(() => restaurarBordesCard(), 500);
            }
            document.getElementById('score-val').innerText = estrellasTotales;
        }

        function procesarRespuestaArtes() {
            estrellasTotales += 1;
            if(nivelesMaterias['artes'] < 100) nivelesMaterias['artes'] += 1;
            guardarProgreso();
            
            document.getElementById('score-val').innerText = estrellasTotales;
            actualizarBarraProgreso();
            ejecutarMotorJuego();
        }

        function restaurarBordesCard() {
            const tarjeta = document.getElementById('game-card');
            if(['ciencia', 'sociales', 'artes'].includes(seccionActual)) {
                tarjeta.style.borderColor = "var(--morado)";
            } else {
                tarjeta.style.borderColor = "var(--naranja)";
            }
        }

        // CARGA AUTOMÁTICA DE REGISTROS AL INICIAR
        window.onload = function() {
            cargarProgresoGuardado();
        };
    </script>
</body>
</html>
