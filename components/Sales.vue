<template>
  <div>
    <div class="div-logo">
      <img class="img-logo" src="../assets/img/Background (1).png" alt="Logo" />
      <h1 class="title">Saravava</h1>
    </div>

    <carousel class="slider-sales">
      <div class="title-sales" id="sales">EM PROMOÇÃO</div>
      <ol>
        <li v-for="book in books" :key="book.id">
          <div class="on-sale">
            <img :src="book.imageUrl" :alt="book.title" />
            <p class="p-books">
              {{ book.title }} <br />
              <span>por {{ book.author }}</span>
            </p>
            <p>
              De {{ book.originalPrice }} <br />
              <span class="price">Por {{ book.discountedPrice }}</span>
            </p>
          </div>
        </li>
      </ol>
    </carousel>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { books } from '~/mock/sales';

export default defineComponent({
  name: 'SalesCarousel',
  data() {
    return {
      books,
    };
  },
});
</script>

<style scoped>
.div-logo {
  height: 160px;
  width: 100%;
  background-color: #ff8400;
  margin-bottom: 60px;
}

.img-logo {
  height: 150px;
  width: 200px;
  margin: 5px 20px;
}

.title {
  display: grid;
  justify-items: center;
  margin-top: -100px;
  font-size: 50px;
}

.title-sales {
  background-color: #faebd7;
  height: 100px;
  align-content: center;
  margin-top: -60px;
  margin-bottom: -20px;
  font-size: 24px;
}

#sales {
  display: grid;
  justify-content: center;
}

.slider-sales {
  background-color: #faebd7;
}

img {
  height: 250px;
  width: 200px;
  margin: 5px 20px;
}

a {
  cursor: pointer;
  text-decoration: none;
  color: green;
}

p {
  display: flex;
  align-items: center;
}

ol {
  flex-direction: row;
  background-color: #faebd7;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  padding: 0;
  margin: 0;
  list-style-type: none;
  align-content: center;
  justify-content: center;
}

li {
  display: flex;
  border: 1px solid #949494;
  border-radius: 30px;
  height: 350px;
  width: 250px;
  margin: 10px;
  justify-content: center;
  align-content: center;
  padding: 20px;
  justify-content: center;
}

.price {
  color: #109010;
}

span {
  color: black;
  font-size: 16px;
  font-weight: normal;
}

.p-books {
  font-size: 19px;
  font-weight: bold;
}
</style>
