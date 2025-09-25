<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>El Conjuro 4</title>

  <!-- Bootstrap 5 CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">

  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: Arial, sans-serif; line-height: 1.6; background: #111; color: #fff; }

    /* Navbar */  
    header {
      background: #111;
      padding: 15px;
      position: sticky;
      top: 0;
      z-index: 10;
    }
    nav ul {
      list-style: none;
      display: flex;
      justify-content: center;
      gap: 20px;
    }
    nav a {
      color: #fff;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:hover { color: #f33; }

    /* Banner */
    .banner {
      text-align: center;
      background: url('https://gestion.pe/resizer/v2/KZZZZT4PYZG2REG2C3FZMBGXTQ.jpg?auth=9edda6e790c8b1e0cf7e4a1858ccfa5d80fc693cf29a03a6dd417b73a579b320&width=1200&height=682&quality=75&smart=true') no-repeat center/cover;
      color: white;
      padding: 120px 20px;
      position: relative;
    }
    .banner::before {
      content: "";
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.5);
    }
    .banner h1, .banner .btn, .banner .estreno, .banner .countdown {
      position: relative;
      z-index: 1;
    }
    .banner h1 { font-size: 3rem; margin: 15px 0; }
    .estreno {
      background: red;
      padding: 8px 15px;
      border-radius: 5px;
      font-weight: bold;
      display: inline-block;
    }
    .countdown {
      margin-top: 15px;
      font-size: 1.2rem;
      font-weight: bold;
    }
   
    /* Trailer */
    .trailer {
      text-align: center;
      padding: 50px 20px;
      background: #000; /* Fondo oscuro */
    }

    /* Sinopsis */
    .sinopsis .contenedor {
      display: flex;
      gap: 20px;
      padding: 50px 20px;
      align-items: center;
      flex-wrap: wrap;
      color: #fff;
    }
    .sinopsis img {
      width: 300px;
      border-radius: 10px;
    }
    .sinopsis p {
      max-width: 600px;
      text-align: justify;
    }

    /* Galería - Elenco */
    .galeria {
      padding: 50px 20px;
      text-align: center;
      background: #000000;
    }
    .galeria h2 {
      margin-bottom: 20px;
    }
    .galeria .grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr); /* 4 columnas fijas */
      gap: 20px;
      margin-top: 20px;
    }
    .actor img {
      width: 100%;
      border-radius: 8px;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .actor img:hover {
      transform: scale(1.05);
      box-shadow: 0 4px 15px rgba(0,0,0,0.5);
    }
    .actor h3 {
      margin-top: 10px;
      font-size: 1rem;
      color: #fff;
    }
    @media (max-width: 768px) {
      .galeria .grid {
        grid-template-columns: repeat(2, 1fr); /* En móviles: 2 columnas */
      }
    }

    /* Carrusel */
    .carrusel {
      padding: 50px 50px;
      background: #000;
      text-align: center;
    }
    .carrusel img {
      height: 500px;      /* más pequeño que ocupar toda la pantalla */
      object-fit: cover;  /* recorta sin deformar */
      img-align:center;
    }

    /* Formulario */
    .contacto {
      padding: 50px 20px;
      background: #111;
      color: #fff;
    }
    .contacto form {
      display: flex;
      flex-direction: column;
      gap: 15px;
      max-width: 500px;
      margin: auto;
    }
    .contacto input, .contacto textarea {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .contacto button {
      background: red;
      color: white;
      border: none;
      padding: 10px;
      cursor: pointer;
      border-radius: 5px;
    }
    .contacto button:hover { background: darkred; }

    /* Footer */
    footer {
      display: flex;
      justify-content: space-around;
      padding: 30px 20px;
      background: #000000;
      color: white;
      flex-wrap: wrap;
      gap: 20px;
      text-align: center;
    }
    footer .ficha, footer .redes, footer .copy {
      flex: 1;
      min-width: 250px;
    }
    footer a {
      color: #f33;
      text-decoration: none;
    }

    .actor img {
  width: 100%;
  height: 300px;        /* Fuerza una altura fija en la imagen */
  object-fit: cover;    /* recorta la imagen sin defromarla */
  border-radius: 8px;
  transition: transform 0.3s, box-shadow 0.3s;
}
  </style>
</head>
<body>

  <!-- 🔹 Navbar -->
  <header>
    <nav>
      <ul>
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#trailer">Tráiler</a></li>
        <li><a href="#sinopsis">Sinopsis</a></li>
        <li><a href="#galeria">Elenco</a></li>
        <li><a href="#contacto">Contacto</a></li>
      </ul>
    </nav>
  </header>

  <!-- 🔹 Banner -->
  <section id="inicio" class="banner">
    <div class="estreno">Estreno: 5 de septiembre del 2025</div>
    <h1>El Conjuro 4</h1>
    <div class="countdown" id="countdown"></div>
  </section>

<!-- 🔹 Tráiler -->
<section id="trailer" class="trailer">
  <h2>Tráiler Oficial</h2>
  <div class="ratio ratio-16x9">
    <iframe 
  src="https://www.youtube.com/embed/HFEoFlccCr0" 
  title="Tráiler oficial El Conjuro 4" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

  </div>
</section>

  <!-- 🔹 Sinopsis -->
  <section id="sinopsis" class="sinopsis">
    <div class="contenedor">
      <img src="https://www.infobae.com/resizer/v2/XC7HGVRFGFDVJMGWEC5GOVJL54.jpg?auth=851cc0f1f3c0ffa0e1fa2179dd6cc01c7aab74683a05972a875b06059859bf4f&smart=true&width=992&height=1240&quality=85" alt="El Conjuro 4">
      <div class="texto">
        <h2>Sinopsis</h2>
        <p>
          La familia en la que se inspira la cinta acudió a sacerdotes y expertos en lo paranormal, pero nadie los ayudó. Años pasaron bajo los abusos de las entes malignos que habitaban su casa y, en 1986, su historia llegó a oídos de los Warren, quienes ya estaban jubilados, pero la atrocidad de los hechos los motivó a atender uno de sus últimos casos.
        </p>
      </div>
    </div>
  </section>

  <!-- 🔹 Elenco -->
  <section id="galeria" class="galeria">
    <h2>Elenco Principal</h2>
    <div class="grid">
      <div class="actor"><img src="https://i.pinimg.com/736x/46/a6/07/46a6075496d25b5cf5f05dc2fade1629.jpg" alt="Veronica Farminga"><h3>Veronica Farminga</h3></div>
      <div class="actor"><img src="https://upload.wikimedia.org/wikipedia/commons/b/b3/PatrickWilson-byPhilipRomano.jpg" alt="Actor 2"><h3>Patrick Wilson</h3></div>
      <div class="actor"><img src="https://upload.wikimedia.org/wikipedia/commons/9/9a/Elliot_Cowan_-_MUSE_%28Portrait%29.jpg" alt="Actor 3"><h3>Elliot Cowan</h3></div>
      <div class="actor"><img src="https://upload.wikimedia.org/wikipedia/commons/a/a9/Ben_Hardy_by_Gage_Skidmore.jpg" alt="Actor 4"><h3>Ben Hardy</h3></div>
      <div class="actor"><img src="https://static.wikia.nocookie.net/starwars/images/c/c4/BeauGadson.jpg/revision/latest?cb=20180125104309" alt="Actor 5"><h3>Beau Gadson</h3></div>
      <div class="actor"><img src="https://static.tvtropes.org/pmwiki/pub/images/john_brotherton.jpg" alt="Actor 6"><h3>Jhon Brotherton</h3></div>
      <div class="actor"><img src="https://i.pinimg.com/736x/59/56/71/595671763a33b923df30afa57694847e.jpg" alt="Actor 7"><h3>Mia Tomlinson</h3></div>
      <div class="actor"><img src="https://image.tmdb.org/t/p/original/iGhPYTNZWYXzMgp0EWKJCuWnevZ.jpg" alt="Actor 8"><h3>Madison Lawlor</h3></div>
      <div class="actor"><img src="https://webservice.mymovies.dk/PhotosInherited/0f860d18-46a2-49c8-a8b8-f95098dd301f.jpg" alt="Actor 9"><h3>Kate Fahy</h3></div>
      <div class="actor"><img src="https://upload.wikimedia.org/wikipedia/commons/e/ef/Shannon_Kook_2014.jpg" alt="Actor 10"><h3>Shannon Kook</h3></div>
      <div class="actor"><img src="https://image.tmdb.org/t/p/original/A43USnarLnfWXDvWimT24cPVfEm.jpg" alt="Actor 11"><h3>Rebecca Calder</h3></div>
      <div class="actor"><img src="https://static.wikia.nocookie.net/walkingdead/images/c/c1/Steve-Coulter-IHA-018677.jpg/revision/latest?cb=20150309215957" alt="Actor 12"><h3>Steve Coulter</h3></div>
    </div>
  </section>

<!-- 🔹 Carrusel Bootstrap -->
  <section class="carrusel">
    <h2>Cronología</h2>
    <div id="carouselExampleCaptions" class="carousel slide">
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
      </div>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="https://4.bp.blogspot.com/-ABwJck0sZ0Q/UhNE0xUrrjI/AAAAAAAAAKI/I0RDnj1rB2c/s400/972170_193475404156819_5100798_n.jpg" class="d-block w-100" alt="Poster 1">
          <div class="carousel-caption d-none d-md-block">
            <h5></h5>
          </div>
        </div>
        <div class="carousel-item">
          <img src="https://www.themarkethink.com/wp-content/uploads/2016/07/conjuro2.jpg" class="d-block w-100" alt="Poster 2">
          <div class="carousel-caption d-none d-md-block">
          </div>
        </div>
        <div class="carousel-item">
          <img src="https://telocuentotodo.com/wp-content/uploads/2021/04/Conjuro-3.jpg" class="d-block w-100" alt="Poster 3">
          <div class="carousel-caption d-none d-md-block">
          </div>
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Anterior</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Siguiente</span>
      </button>
    </div>
  </section>

<!-- 🔹 Formulario -->
  <section id="contacto" class="contacto">
    <h2>Contáctanos</h2>
    <form>
      <input type="text" placeholder="Nombre" required>
      <input type="email" placeholder="Correo" required>
      <textarea placeholder="Mensaje" required></textarea>
      <button type="submit">Enviar</button>
    </form>
  </section>

  <!-- 🔹 Footer -->
  <footer>
    <div class="ficha">
      <h3>Ficha Técnica</h3>
      <p><strong>Título de industria: </strong> Subsidiaria entretenimiento</p>
      <p><strong>Fundacion: </strong> 4 de abril de 1923</p>
      <p><strong>Fundador: </strong> Harry Warner, Albert Warner, San Warner, Jack L. Warner</p>
      <p><strong>Sede central:</strong> California - Estado Unidos</p>
      <p><strong>Coordenadas: </strong> 34°08′59″N 118°20′31″O</p>
    </div>
    <div class="redes">
      <h3>Síguenos</h3>
    <!--  TARGET BLANK PARA NUEVA PAGINA AL PRESIONAR LA RED SOCIAL//////
      EL LINK DE ACCESO SE PONE EN EL HREF Y LQO UE SE MUESTRA ES EL IMG SRC  -->
      <a href="https://www.facebook.com/ConjuringMovies" target="_blank">
    <img src="https://static.vecteezy.com/system/resources/previews/016/716/481/non_2x/facebook-icon-free-png.png" alt="Facebook" width="32" height="32">
    </a>
    <a href="https://www.instagram.com/conjuringmovie/" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Instagram_logo_2022.svg/1200px-Instagram_logo_2022.svg.png" alt="Instagram" width="32" height="32">
    </a>
    <a href="https://twitter.com/conjuringmovies" target="_blank">
    <img src="https://clipground.com/images/logo-de-twitter-png-1.png" alt="Twitter" width="32" height="32">
    </a>
    </div>
    <div class="copy">
      <p>&copy; 2025 Warner Bros. Todos los derechos reservados.</p>
      <img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/7519b96c-71f8-4040-82d4-c80e18384f1b/dfppbl7-f1449527-af03-497a-a939-0008efde006e.png/v1/fill/w_1280,h_1117,strp/warner_bros__logo_1998_2020_background_by_wbblackofficial_dfppbl7-fullview.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9MTExNyIsInBhdGgiOiJcL2ZcLzc1MTliOTZjLTcxZjgtNDA0MC04MmQ0LWM4MGUxODM4NGYxYlwvZGZwcGJsNy1mMTQ0OTUyNy1hZjAzLTQ5N2EtYTkzOS0wMDA4ZWZkZTAwNmUucG5nIiwid2lkdGgiOiI8PTEyODAifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6aW1hZ2Uub3BlcmF0aW9ucyJdfQ.c1xrDPYTFLVSqkBMmdKlRrVDw-Rckqw1EI7JqcUBgcE" alt="Warner Bros" width="64" height="64">
    </div>
    </div>
  </footer>

  <!-- Bootstrap 5 JS -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
