<template>
    <div class="backdrop">
        <div class="modal-loading">
            <h1 v-if='checking'>Is <span class="gerecht">{{ gerecht }}</span> lekker met sambal?</h1>
            <div class="result" v-if="result">
                <h1>YES!!!!</h1>
                <p><span class="gerecht">{{ gerecht }}</span> is fakking lekker met sambal!</p>
                <button @click=btnClickHandler>Back</button>
            </div>
            <h5 v-if='checking'>We gaan het checken!</h5>
            <p v-if='checking'>{{ loading }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['gerecht', 'loading', 'result', 'checking', 'btnClickHandler'],
    methods: {
        back() {
            console.log("clicked back")
            this.callback()
        }
    }
}
</script>

<style scoped>
    .modal-loading {
      align-self: center;
      width: 300px;
      height: 200px;
      padding: 20px;
      margin: 200px auto;
      background: rgba(255, 255, 255, 0.849);
      border-radius: 10px;
      display: flex;
      align-content: center;
      justify-content: center;
      flex-direction: column;
    }   
    .modal-loading h1 {
      color: rgba(0, 0, 0, 0.795);
      font-size: 20px;
      font-family: 'Staatliches', cursive;
      text-align: center;
    }   
    .modal-loading h5 {
      color: black;
      font-size: 20px;
      font-family: 'Staatliches', cursive;
      text-align: center;
      color: rgba(0, 0, 0, 0.795);
    }   
    .modal-loading p {
      color: black;
      font-size: 12px;
      font-family: 'Staatliches', cursive;
      text-align: center;
    }   
    .backdrop {
      top: 0;
      position: fixed;
      background: rgba(0, 0, 0, 0.466);
      width: 100%;
      height: 100%;
    }   
    .gerecht {
      color: brown;
    }
    .result {
      display: flex;
      justify-content: center;
      align-content: center;
      flex-direction: column;
    }   
    .loading-text {
      font-size: 8px;
    }   
    .result h1 {
      color: rgba(0, 0, 0, 0.822);
      font-size: 75px;
      margin-top: 7px;
      margin-bottom: 0;
    }   
    .result p {
      font-size: 20px;
    }   
    .result button {
      -webkit-border-radius: 20px;
      -moz-border-radius: 20px;
      position: relative;
      border: none;
      border-radius: 20px;
      width: fit-content;
      color: #000000;
      font-family: 'Staatliches', cursive;
      font-size: 12px;
      background-color: rgba(240, 248, 255, 0.829);
      text-shadow: 1px 1px 20px #000000;
      text-decoration: none;
      display: inline-block;
      cursor: pointer;
      text-align: center;
    }

    .result button:hover {
      background: #ff0000d2;
      -webkit-border-radius: 20px;
      -moz-border-radius: 20px;
      border-radius: 20px;
      text-decoration: none;
    }






</style>