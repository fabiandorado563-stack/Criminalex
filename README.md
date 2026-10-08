# Criminalex
Sitio web oficial de Criminalex
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="CRIMINALEX - Bufete especializado en Derecho Penal y Criminología. Orientación y asesoría jurídica.">
<title>CRIMINALEX | Derecho Penal & Criminología</title>
<style>
:root{
  --bg:#090b0f; --panel:#11151c; --panel2:#171c24; --text:#f4f4f2;
  --muted:#a9afb9; --gold:#c8a96b; --gold2:#e0c487; --line:#252b35;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:Inter,Arial,sans-serif;background:var(--bg);color:var(--text);line-height:1.6}
a{text-decoration:none;color:inherit}
.container{width:min(1120px,92%);margin:auto}
header{position:fixed;top:0;left:0;right:0;z-index:20;background:rgba(9,11,15,.88);backdrop-filter:blur(14px);border-bottom:1px solid rgba(255,255,255,.06)}
.nav{height:76px;display:flex;align-items:center;justify-content:space-between}
.logo{font-size:25px;font-weight:900;letter-spacing:3px}.logo span{color:var(--gold)}
nav{display:flex;gap:28px;color:#d5d7dc;font-size:14px}
nav a:hover{color:var(--gold2)}
.menu{display:none;background:none;border:0;color:white;font-size:26px}
.hero{min-height:100vh;padding:150px 0 90px;display:flex;align-items:center;background:
radial-gradient(circle at 80% 30%,rgba(200,169,107,.13),transparent 30%),
linear-gradient(120deg,#090b0f 45%,#0d1117)}
.hero-grid{display:grid;grid-template-columns:1.25fr .75fr;gap:70px;align-items:center}
.badge{display:inline-block;border:1px solid rgba(200,169,107,.4);color:var(--gold2);padding:7px 13px;border-radius:999px;font-size:12px;letter-spacing:1.4px;text-transform:uppercase;margin-bottom:22px}
h1{font-size:clamp(46px,7vw,82px);line-height:.98;letter-spacing:-3px;margin-bottom:25px}
h1 span{color:var(--gold)}
.hero p{font-size:18px;color:var(--muted);max-width:650px;margin-bottom:32px}
.buttons{display:flex;gap:13px;flex-wrap:wrap}
.btn{display:inline-flex;padding:13px 20px;border-radius:7px;font-weight:700;border:1px solid var(--gold)}
.primary{background:var(--gold);color:#101010}.primary:hover{background:var(--gold2)}
.secondary{color:white}.secondary:hover{background:var(--panel2)}
.hero-card{background:linear-gradient(145deg,#171c24,#0d1015);border:1px solid var(--line);padding:34px;border-radius:16px;box-shadow:0 25px 70px rgba(0,0,0,.4)}
.shield{font-size:48px;color:var(--gold);margin-bottom:15px}
.hero-card h3{font-size:22px;margin-bottom:10px}.hero-card p{font-size:15px;margin:0}
section{padding:100px 0}
.section-title{font-size:38px;line-height:1.1;margin-bottom:12px}.section-title span{color:var(--gold)}
.lead{color:var(--muted);max-width:700px;margin-bottom:42px}
.cards{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.card{background:var(--panel);border:1px solid var(--line);padding:28px;border-radius:12px;transition:.25s}
.card:hover{transform:translateY(-4px);border-color:#5d4d31}
.icon{font-size:28px;color:var(--gold);margin-bottom:18px}.card h3{margin-bottom:9px}.card p{color:var(--muted);font-size:14px}
.about{background:#0c0f14}.about-grid{display:grid;grid-template-columns:.8fr 1.2fr;gap:60px;align-items:center}
.quote{border-left:3px solid var(--gold);padding-left:25px;font-size:25px;line-height:1.35}
.list{margin-top:25px;display:grid;gap:12px;color:#c7cbd1}.list div::before{content:"✓";color:var(--gold);margin-right:10px;font-weight:bold}
.process{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;counter-reset:steps}
.step{position:relative;padding:30px;background:var(--panel);border:1px solid var(--line);border-radius:12px}
.step:before{counter-increment:steps;content:"0" counter(steps);color:var(--gold);font-size:12px;letter-spacing:2px}
.step h3{margin:13px 0 7px}.step p{color:var(--muted);font-size:14px}
.contact{background:linear-gradient(135deg,#12171e,#0b0e13)}
.contact-grid{display:grid;grid-template-columns:.8fr 1.2fr;gap:45px}
.info p{color:var(--muted);margin:12px 0 25px}
form{display:grid;gap:13px}
input,textarea,select{width:100%;background:#0a0d12;border:1px solid var(--line);color:white;padding:14px;border-radius:7px;font:inherit}
textarea{min-height:130px;resize:vertical}
footer{border-top:1px solid var(--line);padding:28px 0;color:#777f8b;font-size:13px}
.footer-flex{display:flex;justify-content:space-between;gap:20px}

.client-area{background:#0a0d12;border-top:1px solid var(--line);border-bottom:1px solid var(--line)}
.client-header{display:flex;justify-content:space-between;align-items:center;gap:30px}
.client-lock{font-size:58px;background:var(--panel);border:1px solid var(--line);width:120px;height:120px;display:grid;place-items:center;border-radius:18px}
.client-grid{display:grid;grid-template-columns:1fr 1fr;gap:18px}
.client-login form,.question-card form{margin-top:20px;display:grid;gap:12px}
.case-result{margin-top:16px;color:var(--gold2);font-size:14px;min-height:20px}

@media(max-width:800px){
 nav{display:none}.menu{display:block}
 .hero-grid,.about-grid,.contact-grid,.client-grid{grid-template-columns:1fr}
 .hero{padding-top:125px}.cards,.process{grid-template-columns:1fr}.client-header{align-items:flex-start}.client-lock{display:none}
 h1{letter-spacing:-2px}.hero-card{display:none}
 .footer-flex{flex-direction:column}
}
</style>
</head>
<body>
<header>
  <div class="container nav">
    <a class="logo" href="#">CRIMINA<span>LEX</span></a>
    <nav>
      <a href="#especialidades">Especialidades</a>
      <a href="#nosotros">Nosotros</a>
      <a href="#proceso">Cómo funciona</a>
      <a href="#contacto">Consulta</a>
      <a href="#clientes">Mi caso</a>
    </nav>
    <button class="menu" aria-label="Abrir menú" onclick="document.querySelector('nav').style.display='flex'">☰</button>
  </div>
</header>

<main>
<section class="hero">
<div class="container hero-grid">
<div>
<div class="badge">Derecho Penal & Criminología</div>
<h1>Defendemos tus <span>derechos.</span></h1>
<p>CRIMINALEX es un bufete especializado en Derecho Penal y Criminología. Un espacio donde puedes explicar tu situación, recibir orientación inicial y encontrar asesoría jurídica profesional.</p>
<div class="buttons">
<a class="btn primary" href="#contacto">Solicitar asesoría</a>
<a class="btn secondary" href="#especialidades">Ver especialidades</a>
</div>
</div>
<div class="hero-card">
<div class="shield">⚖</div>
<h3>Tu caso merece ser escuchado.</h3>
<p>Cuéntanos qué sucede. Nuestro equipo analizará la situación y te orientará sobre las posibles vías de actuación.</p>
</div>
</div>
</section>

<section id="especialidades">
<div class="container">
<h2 class="section-title">Especializados en <span>lo penal.</span></h2>
<p class="lead">Atención centrada en la prevención, orientación, defensa y análisis de situaciones relacionadas con el ámbito penal y criminológico.</p>
<div class="cards">
<div class="card"><div class="icon">⚖</div><h3>Derecho Penal</h3><p>Orientación y defensa en asuntos penales, denuncias, investigaciones, procesos y otras situaciones jurídicas.</p></div>
<div class="card"><div class="icon">⌕</div><h3>Criminología</h3><p>Análisis del fenómeno criminal, conducta delictiva, prevención y evaluación de factores relacionados con el delito.</p></div>
<div class="card"><div class="icon">▣</div><h3>Asesoría jurídica</h3><p>Un primer espacio para explicar tu problema, conocer tus opciones y determinar qué asesoramiento necesitas.</p></div>
</div>
</div>
</section>

<section class="about" id="nosotros">
<div class="container about-grid">
<div>
<div class="badge">CRIMINALEX</div>
<div class="quote">“La justicia comienza cuando una persona puede ser escuchada y comprendida.”</div>
</div>
<div>
<h2 class="section-title">Un equipo para <span>orientarte.</span></h2>
<p class="lead">Nuestro propósito es acercar la asesoría especializada a cualquier persona que necesite entender su situación jurídica y tomar decisiones informadas.</p>
<div class="list">
<div>Atención inicial para explicar tu caso</div>
<div>Orientación clara, profesional y confidencial</div>
<div>Especialización en Derecho Penal y Criminología</div>
<div>Evaluación de alternativas jurídicas</div>
</div>
</div>
</div>
</section>

<section id="proceso">
<div class="container">
<h2 class="section-title">¿Cómo funciona?</h2>
<p class="lead">Un proceso sencillo para que puedas dar el primer paso sin necesidad de conocer de leyes.</p>
<div class="process">
<div class="step"><h3>Cuéntanos</h3><p>Describe brevemente qué ocurrió y qué necesitas. No hace falta utilizar lenguaje jurídico.</p></div>
<div class="step"><h3>Analizamos</h3><p>Revisamos la información proporcionada y determinamos qué área jurídica puede corresponder.</p></div>
<div class="step"><h3>Te orientamos</h3><p>Recibes información sobre las posibles alternativas y, si corresponde, puedes solicitar una asesoría profesional.</p></div>
</div>
</div>
</section>


<section id="clientes" class="client-area">
<div class="container">
  <div class="client-header">
    <div>
      <div class="badge">Área privada del cliente</div>
      <h2 class="section-title">Consulta el estado de <span>tu caso.</span></h2>
      <p class="lead">Si CRIMINALEX ya aceptó tu caso, puedes ingresar tus datos para consultar información y enviar preguntas directamente a tu equipo jurídico.</p>
    </div>
    <div class="client-lock">🔒</div>
  </div>

  <div class="client-grid">
    <div class="card client-login">
      <div class="icon">▣</div>
      <h3>Consultar mi caso</h3>
      <p>Introduce el código que te proporcionó CRIMINALEX y tu número de identificación.</p>
      <form onsubmit="consultarCaso(event)">
        <input id="codigoCaso" placeholder="Código de caso (ej. CRX-2026-001)" required>
        <input id="identificacion" placeholder="C.I. / Identificación" required>
        <button class="btn primary" type="submit">Consultar estado</button>
      </form>
      <div id="resultadoCaso" class="case-result"></div>
    </div>

    <div class="card question-card">
      <div class="icon">?</div>
      <h3>¿Tienes una pregunta?</h3>
      <p>Los clientes con un caso activo pueden enviar una consulta a su equipo de abogados.</p>
      <form onsubmit="enviarPregunta(event)">
        <input id="codigoPregunta" placeholder="Código de caso" required>
        <textarea id="pregunta" placeholder="Escribe tu pregunta..." required></textarea>
        <button class="btn secondary" type="submit">Enviar pregunta</button>
      </form>
    </div>
  </div>
</div>
</section>

<section class="contact" id="contacto">
<div class="container contact-grid">
<div class="info">
<div class="badge">Consulta inicial</div>
<h2 class="section-title">¿Necesitas <span>asesoría?</span></h2>
<p>Escríbenos. Puedes contarnos tu situación de manera breve y solicitar que un profesional se comunique contigo.</p>
<p><strong>Importante:</strong> este formulario es únicamente un medio de contacto y no sustituye una consulta jurídica profesional.</p>
</div>
<form onsubmit="enviar(event)">
<input id="nombre" placeholder="Nombre completo" required>
<input id="contacto" placeholder="Teléfono o WhatsApp" required>
<select id="area">
<option>Derecho Penal</option><option>Criminología</option><option>Otra consulta</option>
</select>
<textarea id="mensaje" placeholder="Cuéntanos brevemente qué ocurrió..." required></textarea>
<button class="btn primary" type="submit">Enviar consulta</button>
</form>
</div>
</section>
</main>

<footer>
<div class="container footer-flex">
<div>© 2026 CRIMINALEX. Todos los derechos reservados.</div>
<div>Derecho Penal · Criminología · Asesoría</div>
</div>
</footer>

<script>
function enviar(e){
 e.preventDefault();
 const nombre=document.getElementById('nombre').value;
 const contacto=document.getElementById('contacto').value;
 const area=document.getElementById('area').value;
 const mensaje=document.getElementById('mensaje').value;
 const texto=`Hola, soy ${nombre}. Mi contacto es ${contacto}. Necesito asesoría en ${area}. Mi consulta: ${mensaje}`;
 const numero="59170000000";
 window.open("https://wa.me/"+numero+"?text="+encodeURIComponent(texto),"_blank");
}

function consultarCaso(e){
 e.preventDefault();
 const codigo=document.getElementById('codigoCaso').value.trim();
 const identificacion=document.getElementById('identificacion').value.trim();
 const resultado=document.getElementById('resultadoCaso');
 resultado.innerHTML=`<strong>Solicitud recibida.</strong><br>Estamos verificando el caso <strong>${codigo}</strong>. En una versión conectada a la base de datos de CRIMINALEX, aquí aparecerían el estado, próximas actuaciones, fechas importantes y mensajes de tu abogado.`;
}
function enviarPregunta(e){
 e.preventDefault();
 const codigo=document.getElementById('codigoPregunta').value.trim();
 const pregunta=document.getElementById('pregunta').value.trim();
 const numero="59170000000";
 const texto=`CRIMINALEX - Consulta de cliente. Código de caso: ${codigo}. Pregunta: ${pregunta}`;
 window.open("https://wa.me/"+numero+"?text="+encodeURIComponent(texto),"_blank");
}
</script>
</body>
</html>
