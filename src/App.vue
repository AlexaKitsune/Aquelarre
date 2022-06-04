<template>
  <AquelarreMain/>
</template>

<script>
import AquelarreMain from './components/AquelarreMain.vue';
export default {
  name: 'App',
  components: {
    AquelarreMain
  },

  methods:{
    setfullscreen(){
      document.body.requestFullscreen();
      window.addEventListener("load",function() {
        setTimeout(function(){ /*This hides the address bar:*/window.scrollTo(0, 1); }, 0);
      });
    }
  },

  mounted(){
    //this.setfullscreen();
  }
}
</script>

<style>

</style>
