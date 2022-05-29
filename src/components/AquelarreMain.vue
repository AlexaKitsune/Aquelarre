<template>
  <main>
    
    <AquelarrePopUp id="popup-MAIN"/>

    <section class="third-L">
      <span>
        <p class="title-main" id="aquelarre_"></p>
        <p class="subtitle-main" id="coven_"></p>
      </span>
    </section>

    <section class="third-Center">
      <AquelarrePentagram v-on:click="showPopUp"/>
    </section>

    <section class="third-R">
      <span>
        <p class="title-main">A</p>
        <p class="subtitle-main">B</p>
      </span>
    </section>

  </main>
</template>

<script>
import AquelarrePentagram from './AquelarrePentagram.vue';
import AquelarrePopUp from './AquelarrePopUp.vue';
export default {
  name: 'AquelarreMain',
  components: {
    AquelarrePentagram,
    AquelarrePopUp
  },

  mounted(){
    this.setName('El Aquelarre', '#aquelarre_', 1400);
    this.setName('The Coven', '#coven_', 3100);
  },

  methods:{

    setName(text, where, delay){
      const Alexa = text;
      let nameAlexa = Alexa.split('');

      const wait = (ms) => new Promise(resolve => setTimeout(resolve, ms));
      const loop = async () => {

        for (let i=0; i<nameAlexa.length; i++){
          if(i==0){ await wait(delay); }
          //console.log(nameAlexa[i]);
          document.querySelector(where).innerHTML += nameAlexa[i];
        await wait(100);}

      }
      loop();
      /*function resetText(ms){
        setTimeout(function(){
          document.querySelector(where).innerHTML = "";
          loop();
        },ms);
      }
      resetText(10000); resetText(25000); resetText(40000);*/
    },
    
    showPopUp(){
      document.getElementById('popup-MAIN').style.display = "flex";
      document.getElementById('popup-container').className = "popup-appear";
    }

  }

}
</script>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Plus+Jakarta+Sans:ital,wght@0,400;0,700;1,400;1,600&display=swap');

  main{
    width: 100vw;
    height: 100vh;
    display: flex;
    background-color: rgb(24, 33, 51);
  }

  #popup-MAIN{
    display: none;
  }

  .third-L, .third-R{
    width: 25%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }

  .third-L span, .third-R span{
    width: fit-content;
  }

  .title-main{
    font-family: 'Bebas Neue', cursive;
    font-size: 3vw;
    margin-bottom: -1ch;
    letter-spacing: 0.2ch;
    color:   #00fff0 ;
  }

  .subtitle-main{
    font-family: 'Plus Jakarta Sans', sans-serif;
    letter-spacing: 0.2ch;
    color: orange;
    font-size: 1vw;
  }

  .third-Center{
    width: 50%; 
    display: flex;
    align-items: center;
    justify-content: center;
  }

/*************************************************************************
 * RESPONSIVE
 *************************************************************************/
@media all and (max-width:780px){

  main{
    flex-direction: column;
    overflow-x: hidden;
  }

  .third-L, .third-R{
    width: 100%;
    height: 25%;
  }

  .third-L span, .third-R span{
    margin-bottom: 5vh;
  }

  .third-Center{
    width: 100%;
    height: 50%;
  }

  .title-main{
    font-size: 12vw;
  }
  .subtitle-main{
    font-size: 4vw;
  }

}
</style>
