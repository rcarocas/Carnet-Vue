<template>
  <body>
    <div id="app">
      <div class="p-5 text-center">
        <!-- Button trigger modal -->
        <button
          type="button"
          class="btn btn-primary"
          data-bs-toggle="modal"
          data-bs-target="#exampleModal"
        >
          Ingresar datos
        </button>
      </div>
      <!-- Modal -->
      <div
        class="modal fade"
        id="exampleModal"
        tabindex="-1"
        aria-labelledby="exampleModalLabel"
        aria-hidden="true"
      >
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h1 class="modal-title fs-5" id="exampleModalLabel">
                Ingresar datos
              </h1>
              <button
                type="button"
                class="btn-close"
                data-bs-dismiss="modal"
                aria-label="Close"
              ></button>
            </div>
            <form v-on:submit.prevent="emitirCarnet">
              <div class="modal-body">
                <div>
                  <div>
                    <label for="run">RUN:</label>
                    <input type="text" name="run" id="run" v-model="run" />
                  </div>
                  <div>
                    <label for="nombres">Nombres:</label>
                    <input
                      type="text"
                      name="nombres"
                      id="nombres"
                      v-model="nombres"
                    />
                  </div>
                  <div>
                    <label for="apellidos">Apellidos:</label>
                    <input
                      type="text"
                      name="apellidos"
                      id="apellidos"
                      v-model="apellidos"
                    />
                  </div>
                  <div>
                    <label for="nacionalidad">Nacionalidad:</label>
                    <input
                      type="text"
                      name="nacionalidad"
                      id="nacionalidad"
                      v-model="nacionalidad"
                    />
                  </div>
                  <div>
                    <label for="genero">Género:</label>
                    <select name="genero" id="genero" v-model="genero">
                      <option value="F">Femenino</option>
                      <option value="M">Masculino</option>
                    </select>
                  </div>
                  <div>
                    <label for="fechaNacimiento">Fecha de Nacimiento:</label>
                    <input
                      type="text"
                      name="fechaNacimiento"
                      id="fechaNacimiento"
                      v-model="fechaNacimiento"
                    />
                  </div>
                  <div>
                    <label for="numDocumento">Número de documento:</label>
                    <input
                      type="text"
                      name="numDocumento"
                      id="numDocumento"
                      v-model="numDocumento"
                    />
                  </div>
                  <div>
                    <label for="fechaEmision">Fecha de Emisión:</label>
                    <input
                      type="text"
                      name="fechaEmision"
                      id="fechaEmision"
                      v-model="fechaEmision"
                    />
                  </div>
                  <div>
                    <label for="fechaVencimiento">Fecha de Vencimiento:</label>
                    <input
                      type="text"
                      name="fechaVencimiento"
                      id="fechaVencimiento"
                      v-model="fechaVencimiento"
                    />
                  </div>
                  <div>
                    <label for="firma">Firma del titular:</label>
                    <input
                      type="text"
                      name="firma"
                      id="firma"
                      v-model="firma"
                    />
                  </div>
                </div>
              </div>
              <div class="modal-footer">
                <button class="btn btn-primary"
                  type="submit"
                  data-bs-dismiss="modal"
                  >Emitir Cédula</button>
                
              </div>
            </form>
          </div>
        </div>
      </div>
      <div class="carnet">
        <aside>
          <div>
            <span>CEDULA DE INDENTIDAD</span>
            <img width="40" src="./assets/img/chile_bandera.png" alt="" />
          </div>

          <img src="./assets/img/foto_elon.jpg" alt="" />
          <p>RUN {{ run }}</p>
        </aside>

        <main>
          <header>
            <p>REPUBLICA DE CHILE</p>
            <span>SERVICIO DE REGISTRO CIVIL E IDENTIFICACIÓN</span>
          </header>
          <section>
            <article>
              <header>APELLIDOS</header>
              <span>{{ apellidos }}</span>
            </article>
            <article>
              <header>NOMBRES</header>
              <span>{{ nombres }}</span>
            </article>

            <div class="grid-2-colums">
              <article>
                <header>NACIONALIDAD</header>
                <span>{{ nacionalidad }}</span>
              </article>
              <article>
                <header>SEXO</header>
                <span>{{ genero }}</span>
              </article>
            </div>
            <div class="grid-2-colums">
              <article>
                <header>FECHA DE NACIMIENTO</header>
                <span>{{ fechaNacimiento }} </span>
              </article>
              <article>
                <header>NÙMERO DOCUMENTO</header>
                <span>{{ numDocumento }}</span>
              </article>
            </div>
            <div class="grid-2-colums">
              <article>
                <header>FECHA DE EMISIÒN</header>
                <span>{{ fechaEmision }}</span>
              </article>
              <article>
                <header>FECHA DE VENCIMIENTO</header>
                <span>{{ fechaVencimiento }}</span>
              </article>
            </div>
            <article>
              <header>FIRMA DEL TITULAR</header>
              <span>{{ firma }}</span>
            </article>
          </section>
        </main>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      run: "",
      apellidos: "",
      nombres: "",
      nacionalidad: "",
      genero: "",
      fechaNacimiento: "",
      numDocumento: "",
      fechaEmision: "",
      fechaVencimiento: "",
      firma: "",
    };
  },
  methods: {
    emitirCarnet: function () {
      alert("Se ha generado su cédula");
    },
  },
};
</script>

<style>
body {
  display: flex;
  justify-content: center;
  height: 60vh;
  font-size: 10px;
  font-family: sans-serif;
}

.carnet {
  width: 400px;
  height: 230px;
  background: #c8deed;
  border-radius: 20px;
  display: grid;
  grid-template-columns: 30% 1fr;
  padding: 15px;
  box-shadow: 0px 0px 10px 2px black;
  box-sizing: content-box;
}

aside div {
  display: flex;
}

aside > img {
  margin-top: 15px;
  width: 100%;
}

aside p {
  text-align: center;
  font-size: 12px;
  font-weight: bold;
}

main {
  padding: 0px 14px;
}

main article {
  margin: 0px;
}

main article header {
  font-weight: bold;
  color: #0235a4;
  font-size: 8px;
}

main header p {
  font-size: 20px;
  margin: 0;
  font-weight: bold;
  color: #0235a4;
}

main header span {
  font-size: 8px;
  color: #399be1;
}

main section {
  margin-top: 10px;
}

main section article span {
  font-size: 13px;
  font-weight: 600;
}

main section .grid-2-colums {
  display: grid;
  grid-template-columns: 50% 50%;
}
</style>
