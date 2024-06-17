<template>
  <section id="principal">
    <h1 id="nombre" class="animate__animated animate__backInDown">Daniel Martínez</h1>
    <h2 id="titulo" class="animate__animated animate__backInLeft">Developer</h2>
    <p id="texto"></p>
    <img id="yo" src="../public/imgs/yo.jpg">
    <div id="info">
      <p>Lenguajes de programación:</p>
      <p>- Python</p>
      <p>- JavaScript</p>
      <br>
      <p>Herramientas empleadas:</p>
      <p>- Figma</p>
      <p>- Git</p>
      <p>- Cypress</p>
    </div>

    <button class="botones" @click="mostrarTelefono()">Numero de teléfono</button>
    <button class="botones" @click="mostrarEmail()">Correo electrónico</button>

    <footer id="footer">
      <p>Todos los Derechos Reservados.</p>
    </footer>
  </section>
</template>

<script>
import Swal from 'sweetalert2';

export default {
  mounted() {
    function maquinaEscribir(elemento, textoCompleto, velocidad) {
      var i = 0;
      var interval = setInterval(function() {
        if (i < textoCompleto.length) {
          elemento.textContent += textoCompleto.charAt(i);
          i++;
        } else {
          clearInterval(interval);
        }
      }, velocidad);
    }
    
    var parrafo = document.getElementById('texto');
    
    var textoCompleto = "Programador en desarrollo de aplicaciones web. Trabajando con Linux, Proxy's como Nginx, Python, JavaScript, Vue, Git. Dispuesto a aprender cualquier lenguaje, seguir formándome y a continuar creciendo tanto profesionalmente como personalmente.";
    
    maquinaEscribir(parrafo, textoCompleto, 50);
  },
  methods: {
    mostrarTelefono() {
      Swal.fire({
        title: 'Numero de teléfono:',
        text: '+34 656 35 82 29',
        icon: 'info',
        confirmButtonText: 'Aceptar'
      });
    },
    mostrarEmail() {
      Swal.fire({
        title: 'Envíame un correo a:',
        text: 'danielmartiguerrero@gmail.com',
        icon: 'info',
        confirmButtonText: 'Aceptar'
      });
    }
  }
}
</script>


<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

#principal{
  display: flex;
  flex-direction: column;
  align-items: center;
}

#nombre{
  font-size: 40px;
  margin: 20px;
  margin-bottom: 5px;
}

#titulo{
  font-size: 28px;
  margin: 30px;
  margin-top: 5px;
  font-style: italic;
}

#texto{
  margin: 20px;
  width: 38vh;
}

#yo{
  width: 40vh;
  border-radius: 20px;
}

#info{
  margin: 20px;
  width: 38vh;
}

#footer{
  background-color: rgb(223, 223, 223);
  width: 100%;
  text-align: center;
  height: 30px;
  font-weight: bold;
  margin-top: 40px;
}

.botones{
  width: 40vh;
  border-radius: 10px;
  font-weight: bold;
  font-size: 20px;
  height: 50px;
  margin: 10px;
  background-color: rgb(97, 97, 97);
  color: rgb(218, 218, 218);
}
</style>
