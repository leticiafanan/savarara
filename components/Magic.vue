<template>
  <div>
    <div class="div-logo">
      <img class="img-logo" src="/assets/img/Background (1).png" />
      <h1 class="title">Saravava</h1>
    </div>

    <carousel class="carousel-magics">
      <div class="title-magics" id="title-magic">OS MAIS MÁGICOS</div>
      <ol>
        <li v-for="book in books" :key="book.id">
          <div class="magics">
            <img :src="book.image" :alt="book.title" />
            <p class="p-books">{{ book.title }} <br> <span>por {{ book.author }}</span></p>
            <p>{{ book.price }}</p>
          </div>
        </li>
      </ol>
    </carousel>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { books } from '~/mock/magic';

export default defineComponent({
  name: 'BooksCarousel',
  data() {
    return {
      books, 
    };
  },
});
</script>

<style scoped>

.div-logo{
  height: 160px;
  width: 100%;
  background-color: #FF8400;
  margin-bottom: 60px;

}

.img-logo{
  height: 150px;
  width: 200px;
  margin: 5px 20px;
}

.title {
  display: grid;
  justify-items: center;
  margin-top: -100px;

}

.title-magics{
  background-color: #faebd7;
  height: 100px;
  align-content: center;
  margin-top: -60px;
  margin-bottom: -20px;
}

#title-magic{
  display: grid;
  justify-content: center;
  font-size: 24px;
}

.carousel-best-sellers{
  background-color: #faebd7;
}


img {
  height: 250px;
  width: 200px;
  margin: 5px 20px;
}


a{
  cursor: pointer;
  text-decoration: none;
  color: green;
}

p{
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

span{
  color: black;
  font-size: 16px;
  font-weight: normal;
  justify-content: center;
}

.p-books{
  font-size: 19px;
  font-weight: bold;
  justify-content: center;
}
</style>
