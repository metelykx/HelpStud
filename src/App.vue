<script setup>
import { ref } from 'vue';
import logo from './assets/HelpStud.png';
import sideImage from './assets/cfu.png';

const searchQuery = ref('');
</script>

<template>
  <div class="header">
    <img :src="logo" alt="HelpStud Logo" class="logo" />
    <h1 class="title">HelpStud</h1>
    <div class="search-container">
      <input
        v-model="searchQuery"
        type="text"
        placeholder="Поиск предмета..."
        class="search-input"
      />
    </div>
  </div>

  <div class="content">
    <div class="str">
      <h2 class="about-heading">О нас</h2>
      <div class="text-with-image">
        <div class="text">
          <p>
            Университет — это важный шаг во взрослую жизнь, где ты найдёшь друзей, любовь и знания, которые станут основой твоего будущего.
          </p>
          <p class="subjects">
            HelpStud создан, чтобы помочь тебе в обучении по направлениям: Программная инженерия, Информатика и вычислительная техника, Компьютерная безопасность и не только.
          </p>
          <p>
            Здесь ты разберёшься в сложных темах, получишь советы по программированию и другим сферам. Начни учиться уже сейчас и быстрее достигай своих целей!
          </p>
          <p>
            Развивайся и учись вместе с HelpStud!
          </p>
        </div>
        <img :src="sideImage" alt="CFU Image" class="side-image" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 80px;
  position: fixed;
  top: 0;
  left: 0;
  background-color: #007bff;
  padding: 10px 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.logo {
  width: 50px;
  height: auto;
  margin-right: 15px;
}

.title {
  font-size: 25px;
  font-weight: bold;
  color: #ffffff;
  font-family: 'Kanit', sans-serif;
  margin-right: auto;
}

.search-container {
  margin-left: 20px;
  width: 300px;
}

.search-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ffffff;
  border-radius: 10px;
  outline: none;
  transition: border-color 0.3s;
  background-color: rgba(255, 255, 255, 0.1);
  color: #ffffff;
}

.search-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.search-input:focus {
  border-color: #ffffff;
  background-color: rgba(255, 255, 255, 0.2);
}

.content {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  min-height: 100vh;
  padding-top: 12%;
  box-sizing: border-box;
  width: 100%;
}

.str {
  font-family: 'Kanit', sans-serif;
  color: #ffffff;
  line-height: 1.6;
  width: 100%;
  max-width: 1200px;
  padding: 0 30px;
  font-size: 20px;
  text-align: justify;
  margin: 0 auto;
}

.about-heading {
  font-size: 30px;
  font-weight: bold;
  color: #ffffff;
  margin: 10px 10px 20px 90px;
  text-align: center;
  font-family: 'Kanit', sans-serif;
}

.text-with-image {
  display: flex;
  align-items: flex-start;
  gap: 100px;
  width: 100%;
}

.text {
  flex: 1;
  max-width: 800px;
  min-width: 600px;
}

.side-image {
  width: 400px;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  margin-top: 0;
  flex-shrink: 0;
}

.str p {
  margin-bottom: 20px;
  letter-spacing: normal;
  word-spacing: normal;
  max-width: 100%;
}

.str p:last-child {
  margin-bottom: 0;
}
</style>