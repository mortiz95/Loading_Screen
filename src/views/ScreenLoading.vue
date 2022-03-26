<template>
 <ion-page>
  <ion-content>
       <div v-if="isLoading" class="container fadeIn">
         <div class="ring">Loading
            <span></span>
          </div>
        </div>
  </ion-content>
 </ion-page>
</template>

<script>

import { IonPage, IonContent } from '@ionic/vue';

    export default {
       components: {
        IonPage,
        IonContent
     }, 
     data() {
       return {
         isLoading: true
       }
     }
    }

</script>

<style lang="scss" scoped>

body, html {
  height: 100%;
  background: #0C0C0C;
}

.fadeIn {
  animation-name: fadeIn;
  animation-duration: 4s;
}

.container {
    display: flex;
    justify-content: center;
    align-items: end;
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    height: 100%; 
    background-position: center;
    background-repeat: no-repeat;
    background-size: inherit;
    background-image: url('@/assets/landing.png');
}

.ring
{
  position:absolute;
  top:88%;
  left:50%;
  transform:translate(-50%,-50%);
  width:90px;
  height:90px;
  background:transparent;
  border:3px solid #3c3c3c;
  border-radius:50%;
  text-align:center;
  line-height:84px;
  font-family:sans-serif;
  font-size:10px;
  color:#E0A43E;
  letter-spacing:4px;
  text-transform:uppercase;
  text-shadow:0 0 10px #E0A43E;
  box-shadow:0 0 20px rgba(0,0,0,.5);
}

.ring:before
{
  content:'';
  position:absolute;
  top:-3px;
  left:-3px;
  width:100%;
  height:100%;
  border:3px solid transparent;
  border-top:3px solid #E0A43E;
  border-right:3px solid #E0A43E;
  border-radius:50%;
  animation:animateC 2s linear infinite;
}
span
{
  display:block;
  position:absolute;
  top:calc(50% - 2px);
  left:50%;
  width:50%;
  height:4px;
  background:transparent;
  transform-origin:left;
  animation:animate 2s linear infinite;
}
span:before
{
  content:'';
  position:absolute;
  width:16px;
  height:16px;
  border-radius:50%;
  background:#E0A43E;
  top:-6px;
  right:-8px;
  box-shadow:0 0 20px #E0A43E;
}
@keyframes animateC
{
  0%
  {
    transform:rotate(0deg);
  }
  100%
  {
    transform:rotate(360deg);
  }
}
@keyframes animate
{
  0%
  {
    transform:rotate(45deg);
  }
  100%
  {
    transform:rotate(405deg);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

</style>