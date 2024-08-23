<script>
export default {
  name: 'CreditCard',
  data() {
    return {
      form: {
        tituloTarjeta: '',
        chipSrc: 'chip.png',
        numeroTarjeta: '',
        fechaVencimiento: '',
        propietario: '',
        tipotarjeta: 'visa.png'
      }
    }
  }
}
</script>

<template>
  <form>
    <div>
      <label>Título de la tarjeta: </label>
      <input id="tituloTarjeta" type="text" v-model="form.tituloTarjeta" placeholder="Visa Gold" />
    </div>

    <div>
      <label for="chip">Chip SRC: </label>
      <select name="chip" id="chip" v-model="form.chipSrc">
        <option value="">Seleccione un chip</option>
        <option value="/public/chip.png">Standart</option>
        <option value="/public/chip2.png">Premium</option>
        <option value="/public/chip3.png">Gold</option>
      </select>
    </div>

    <div>
      <label for="numero">Número: </label>
      <input
        id="numero"
        type="text"
        v-model="form.numeroTarjeta"
        placeholder="0000 0000 0000 0000"
      />
    </div>

    <div>
      <label>Fecha de expiración: </label>
      <input type="text" v-model="form.fechaVencimiento" placeholder="MM/YY" />
    </div>

    <div>
      <label>Propietario: </label>
      <input type="text" v-model="form.propietario" placeholder="Nombre completo" />
    </div>

    <div>
      <label>Tipo de tarjeta SRC: </label>
      <select name="tipoTarjeta" id="tipoTarjeta" v-model="form.tipotarjeta">
        <option value="">Seleccione una tarjeta</option>
        <option value="/public/visa.png">Visa</option>
        <option value="/public/mastercard.png">MasterCard</option>
        <option value="/public/amexpress.svg">American Express</option>
      </select>
    </div>
  </form>
  <div class="carnet">
    <h3>{{ form.tituloTarjeta }}</h3>
    <img :src="form.chipSrc" class="img-chip" alt="Tipo de chip" />
    <div>
      <h2>{{ form.numeroTarjeta }}</h2>
      <span
        >Fecha Exp: <b>{{ form.fechaVencimiento }}</b></span
      >
    </div>
    <footer>
      <span>{{ form.propietario }}</span>
      <img :src="form.tipotarjeta" class="img-tarjeta" alt="Tipo de tarjeta" />
    </footer>
  </div>
</template>
<style scoped>
form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.carnet {
  width: 400px;
  height: 230px;
  background: #feac5e; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to bottom,
    #4bc0c8,
    #c779d0,
    #feac5e
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to bottom,
    #4bc0c8,
    #c779d0,
    #feac5e
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  color: rgb(58, 19, 109);
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 6px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

.img-chip,
.img-tarjeta {
  width: 60px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
