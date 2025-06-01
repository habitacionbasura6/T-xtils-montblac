<!DOCTYPE html>
<html lang="ca">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Tèxtils Montblanc</title>
  <style>
    /* Estilos Globales */
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      font-family: 'Arial', sans-serif;
      overflow-x: hidden;
    }

    /* Fondo y efectos */
    .hero {
      background-image: url('https://images.pexels.com/photos/196662/pexels-photo-196662.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1');
      background-size: cover;
      background-position: center;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      color: white;
      text-align: center;
      overflow: hidden;
    }

    /* Elementos visuales de nieve */
    .snowflake {
      position: absolute;
      top: -10%;
      width: 50px;
      height: 50px;
      background-color: white;
      border-radius: 50%;
      opacity: 0.6;
      animation: fall 5s linear infinite;
    }

    @keyframes fall {
      0% {
        top: -10%;
        opacity: 0.6;
      }
      100% {
        top: 100%;
        opacity: 0;
      }
    }

    .snowflake:nth-child(odd) {
      animation-duration: 4s;
      animation-delay: 0s;
    }

    .snowflake:nth-child(even) {
      animation-duration: 6s;
      animation-delay: 2s;
    }

    .mountain {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 300px;
      background: url('https://cdn.pixabay.com/photo/2016/11/18/17/01/mountains-1838760_960_720.jpg') no-repeat center bottom;
      background-size: cover;
      z-index: -1;
    }

    .hero h1 {
      font-size: 3.5rem;
      font-weight: bold;
      text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.7);
      margin-bottom: 20px;
    }

    .comenca-btn {
      background-color: #000;
      color: white;
      padding: 15px 30px;
      font-size: 1.2rem;
      text-transform: uppercase;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
    }

    .comenca-btn:hover {
      background-color: #444;
    }

    nav {
      background-color: rgba(0, 0, 0, 0.7);
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      padding: 15px;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 10;
    }

    nav a {
      color: white;
      text-decoration: none;
      margin: 0 15px;
      font-size: 1.1rem;
      font-weight: bold;
    }

    nav a:hover {
      color: #ccc;
    }

    section {
      padding: 50px 20px;
      background-color: #f5f5f5;
      margin-top: 30px;
    }

    section h2 {
      font-size: 2.5rem;
      color: #333;
      margin-bottom: 20px;
    }

    section p, section ul, section ol {
      font-size: 1.1rem;
      color: #666;
      max-width: 900px;
      margin: 0 auto 20px;
    }

    #content-details {
      padding: 50px 20px;
      background-color: #fff;
      display: none;
      max-width: 1000px;
      margin: 0 auto 50px;
    }

    #tienda {
      background-color: #f9f9f9;
      padding: 50px 20px;
      max-width: 1000px;
      margin: 0 auto 50px;
    }

    #tienda h2 {
      font-size: 2.5rem;
      color: #333;
      margin-bottom: 30px;
      text-align: center;
    }

    .products {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      gap: 30px;
    }

    .product {
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      padding: 20px;
      width: 300px;
      text-align: center;
      transition: transform 0.3s ease;
    }

    .product:hover {
      transform: translateY(-10px);
      box-shadow: 0 6px 20px rgba(0,0,0,0.2);
    }

    .product img {
      max-width: 100%;
      height: auto;
      border-radius: 5px;
      margin-bottom: 15px;
    }

    .product h3 {
      font-size: 1.4rem;
      margin-bottom: 10px;
      color: #222;
    }

    .product p {
      font-size: 1rem;
      color: #555;
      margin-bottom: 15px;
    }

    .product p strong {
      font-size: 1.2rem;
      color: #000;
    }

    footer {
      background-color: #222;
      color: white;
      padding: 15px 0;
      text-align: center;
      font-size: 1rem;
    }

    /* Estilos para la sección de contacto */
    #contacte {
      background-color: #f0f0f0;
      padding: 50px 20px;
      max-width: 1000px;
      margin: 0 auto;
    }

    #contacte h2 {
      font-size: 2.5rem;
      color: #333;
      margin-bottom: 20px;
      text-align: center;
    }

    #contacte p {
      font-size: 1.2rem;
      color: #555;
      margin-bottom: 30px;
      text-align: center;
    }

    /* Estilos del formulario de contacto */
    #contacte form {
      max-width: 600px;
      margin: 0 auto;
      background-color: rgba(0, 0, 0, 0.1);
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }

    #contacte form input, #contacte form textarea {
      width: 100%;
      padding: 15px;
      margin-bottom: 20px;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 1rem;
      transition: all 0.3s ease;
    }

    #contacte form input:focus, #contacte form textarea:focus {
      border-color: #4caf50;
      outline: none;
      box-shadow: 0 0 8px rgba(76, 175, 80, 0.5);
    }

    #contacte form button {
      background-color: #000;
      color: white;
      padding: 15px 30px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      font-size: 1.1rem;
      text-transform: uppercase;
      transition: background-color 0.3s ease, transform 0.3s ease;
    }

    #contacte form button:hover {
      background-color: #444;
      transform: translateY(-3px);
    }

    #contacte form button:active {
      background-color: #333;
      transform: translateY(1px);
    }
  </style>
</head>
<body>

  <!-- Menú de Navegación -->
  <nav>
    <a href="#presentacio">Presentació</a>
    <a href="#dades">Dades</a>
    <a href="#objectiu">Objectiu</a>
    <a href="#abast">Abast</a>
    <a href="#condicions">Condicions</a>
    <a href="#necessitats">Necessitats</a>
    <a href="#annexos">Annexos</a>
    <a href="#tienda">Botiga</a>
    <a href="#contacte">Contacte</a>
  </nav>

  <!-- Hero Section -->
  <div class="hero">
    <div>
      <h1>Tèxtils Montblanc</h1>
      <p>Qualitat tèxtil inspirada en la natura i la neu</p>
      <a href="javascript:void(0);" class="comenca-btn" onclick="showContent()">Comença</a>
    </div>
    <!-- Elementos de nieve -->
    <div class="snowflake" style="left: 10%; animation-duration: 5s; animation-delay: 2s;"></div>
    <div class="snowflake" style="left: 30%; animation-duration: 4s; animation-delay: 0.5s;"></div>
    <div class="snowflake" style="left: 50%; animation-duration: 6s; animation-delay: 1.5s;"></div>
    <div class="snowflake" style="left: 70%; animation-duration: 5s; animation-delay: 0.2s;"></div>
    <div class="snowflake" style="left: 90%; animation-duration: 6s; animation-delay: 3s;"></div>
  </div>

  <!-- Montañas -->
  <div class="mountain"></div>

  <!-- Sección Detallada -->
  <div id="content-details">
    <!-- Secciones internas como presentació, dades, etc. (omitido aquí para brevedad) -->
  </div>

  <!-- Sección Tienda -->
  <section id="tienda">
    <h2>Botiga - Equipament de Neu</h2>
    <div class="products">
      <div class="product">
        <img src="https://img.baba-blog.com/2024/02/2024-ski-gloves-selection-a-strategic-guide-to-ma_00.jpg?x-oss-process=style%2Flarge" alt="Guants de Neu" />
        <h3>Guants de Neu</h3>
        <p>Guants tècnics resistents a la neu i al fred intens per a activitats d’hivern.</p>
        <p><strong>€39.99</strong></p>
      </div>
      <div class="product">
        <img src="https://www.walashop.com/media/catalog/product/s/d/sd125405-blk.jpg?quality=80&bg-color=255,255,255&height=900&width=900&canvas=900:900" alt="Pantalons Tècnics de Neu" />
        <h3>Pantalons Tècnics de Neu</h3>
        <p>Pantalons impermeables i transpirables per a esportistes de muntanya.</p>
        <p><strong>€89.99</strong></p>
      </div>
      <div class="product">
        <img src="https://www.walashop.com/media/catalog/product/q/u/quiksilvereqytj03389bsm0_1.jpg?quality=80&bg-color=255,255,255&height=900&width=900&canvas=900:900" alt="Jaqueta Tècnica de Neu" />
        <h3>Jaqueta Tècnica de Neu</h3>
        <p>Protecció avançada contra el fred i la humitat per a esports de muntanya.</p>
        <p><strong>€149.99</strong></p>
      </div>
    </div>
  </section>

  <!-- NUEVA SECCIÓN: CONTACTA'NS -->
  <section id="contacte">
    <h2>Contacta'ns</h2>
    <p>Estem aquí per ajudar-te. Pots posar-te en contacte amb nosaltres a través del formulari següent:</p>
    <form>
      <label for="nom">Nom:</label>
      <input type="text" id="nom" name="nom" required>

      <label for="email">Correu electrònic:</label>
      <input type="email" id="email" name="email" required>

      <label for="missatge">Missatge:</label>
      <textarea id="missatge" name="missatge" rows="5" required></textarea>

      <button type="submit">Enviar</button>
    </form>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 Tèxtils Montblanc. Tots els drets reservats.</p>
  </footer>

  <script>
    function showContent() {
      const content = document.getElementById('content-details');
      if (content.style.display === 'block') {
        content.style.display = 'none';
      } else {
        content.style.display = 'block';
        window.scrollTo({ top: content.offsetTop, behavior: 'smooth' });
      }
    }
  </script>

</body>
</html>
