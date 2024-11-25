<template>
  <div>
    <div class="div-logo">
      <img :src="headerData.logo.src" :alt="headerData.logo.alt" />
      <h1 class="title">{{ headerData.siteTitle }}</h1>
    </div>

    <div class="itens-header">
      <h1>{{ headerData.siteDescription }}</h1>
      <a :href="headerData.siteCTA">{{ headerData.siteCTA }}</a>
    </div>

    <header>
      <div class="login">
        <p>{{ headerData.user.welcomeMessage }}</p>
        <a :href="headerData.user.loginLink">{{ headerData.user.loginCTA }}</a>
      </div>

      <div class="cart">
        <a>
          <img :src="headerData.cart.iconSrc" :alt="headerData.cart.alt" class="img-cart" />
        </a>
      </div>

      <div class="header">
        <a
          v-for="link in headerData.links"
          :key="link.href"
          :href="link.href"
          class="a-header"
        >
          {{ link.label }}
        </a>
      </div>
    </header>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import { headerData } from '~/mock/header';

export default defineComponent({
  name: 'IndexPage',
  data() {
    return {
      headerData,
    };
  },
});
</script>

<style scoped>


.div-logo{
  height: 200px;
  width: 100%;
  background-color: #FF8400;
  margin-bottom: 60px;

}

.title {
  display: grid;
  justify-items: center;
  margin-top: -100px;

}

img {
  height: 150px;
  width: 200px;
  margin: 5px 20px;

}

.login {
  max-width: 100vw;
  max-width: 100vh;
  height: 60px;
  width: 265px;
  display: grid;
  margin-left: 600px;
  padding: -30px;
  margin-top: -159px;
  align-items: center;
}

.p-login {
  padding: 10px;
  margin: 30px;
  margin-right: -65px;

  max-width: 100vw;
  max-width: 100vh;
}

.a-login {
  padding: 10px;
  margin: 30px;

  max-width: 100vw;
  max-width: 100vh;
}

.cart {
  height: 60px;
  width: 160px;
  display: grid;
  margin-left: 680px;
  padding: -30px;
  margin-top: -97px;
  align-items: center;

  max-width: 100vw;
  max-width: 100vh;
}

.img-cart {
  height: 50px;
  width: 70px;

  max-width: 100vw;
  max-width: 100vh;
}

.itens-header{
  height: 56px;
  display: flex;
  align-items: center;
}

header {
  background-color: #faebd7;
  justify-content: center;
  
}

.header {
  background-color: #faebd7;
  height: 210px;
  display: flex;
  margin-top: 300px;
  justify-items: center;
  margin-left: 150px;
  flex-direction: row;
  padding: 2px;
}

.a-header {
  height: 20px;
  padding: 20px;
  justify-items: center;
  border: 1px solid black;
  border-radius: 20px;
  margin-left: 187px;
}

.a-header:hover{
  background-color:#FF8400;
  color: #faebd7;
}

a{
  cursor: pointer;
  text-decoration: none;
  color: green;
}

</style>