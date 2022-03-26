<template>
  <div class="page-loader" v-if="!isloaded">
        <ion-spinner></ion-spinner>
 </div>
  

</template>

<script>
import { IonSpinner } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
    data: () => {
      return {
        isloaded: false
      }
    },
      mounted() {
      document.onreadystatechange = () => {
        if (document.readyState == "complete") { 
          this.isloaded = true;
        } 
      }
    },
    components: { IonSpinner },
    
});
</script>

<style lang="scss" scoped>
  body  {
  background: url("./assets/landing.png") no-repeat center center
  background-color: #cccccc;
}

  
</style>