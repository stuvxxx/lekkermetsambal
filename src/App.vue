<template>
  <div class="wrapper">
    <h1>lekker met sambal?</h1>
      <div class="input-wrapper">
        <input required ref="food" type="text" placeholder="Wat met sambal?" v-model="myInput">
        <button @click="handleToggleLoading">CHECK!</button>
      </div>
  </div>
  <div v-if="showModalLoading">
      <ModalLoading :gerecht = myInput :loading = loading :result = result :checking = checking :btnClickHandler = "this.handleBack">
      </ModalLoading>
  </div>
</template>
Loading


<script>
import ModalLoading from './components/ModalLoading.vue'

const delay = ms => new Promise(res => setTimeout(res, ms));

export default {
  name: 'App',
  components: { ModalLoading },
  data() {
    return {
      loading: "",
      myInput: "",
      checking: true,
      showModalLoading: false,
      result: false
    }
  },

  methods: {
    async handleToggleLoading() {
      if (this.myInput == "") {
        this.myInput = "ALLES"
      }
      this.showModalLoading = !this.showModalLoading
      this.loading = "Chefs raadplegen"
      await delay(500)
      this.loading = "Chefs raadplegen."
      await delay(500)
      this.loading = "Chefs raadplegen.."
      await delay(500)
      this.loading = "Chefs raadplegen..."
      await delay(500)
      this.loading = "Kookboeken nakijken"
      await delay(500)
      this.loading = "Kookboeken nakijken."
      await delay(500)
      this.loading = "Kookboeken nakijken.."
      await delay(500)
      this.loading = "Kookboeken nakijken..."
      await delay(500)
      this.loading = "ff proeven toch"
      await delay(500)
      this.loading = "ff proeven toch."
      await delay(500)
      this.loading = "ff proeven toch.."
      await delay(500)
      this.loading = "ff proeven toch..."
      await delay(500)
      this.loading = "EUHM..."
      await delay(750)
      this.loading = "NOU..."
      await delay(750)
      this.checking = false
      this.result = true
    },
    
    handleBack() {
      console.log("received at handleback")
      this.showModalLoading = !this.showModalLoading
      this.result = !this.result
      this.myInput = ""
      this.checking = true
    }

//    handleToggleResult() {
//      this.showResultModal = !this.showResultModal
//    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Staatliches&display=swap');
  .wrapper {
    padding-top: 140px;
    width: 100%;
    height: 100%;
  }

  .wrapper h1 {
    text-align: center;
    margin: 0 auto;
    margin-bottom: 40px;
    font-size: 48px;
    color: rgba(240, 248, 255, 0.829);
    font-family: 'Staatliches', cursive;
  }

  .input-wrapper {
    margin: 0 auto;
    width: fit-content;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .input-wrapper input {
    margin: 0 auto 20px auto;
    font-size: 20px;
    font-family: 'Staatliches', cursive;
  }

  .input-wrapper button {
   -webkit-border-radius: 20px;
   -moz-border-radius: 20px;
   border: none;
   border-radius: 20px;
   color: #000000;
   font-family: 'Staatliches', cursive;
   font-size: 30px;
   padding: 20px;
  background-color: rgba(240, 248, 255, 0.829);
   -webkit-box-shadow: 5px 5px 52px 0 #000000;
   -moz-box-shadow: 5px 5px 52px 0 #000000;
   box-shadow: 5px 5px 52px 0 #000000;
   text-shadow: 1px 1px 1px #c01b1b;
   text-decoration: none;
   display: inline-block;
   cursor: pointer;
   text-align: center;
}

.input-wrapper button:hover {
   background: #ff0000d2;
   -webkit-border-radius: 20px;
   -moz-border-radius: 20px;
   border-radius: 20px;
   text-decoration: none;
}



</style>
