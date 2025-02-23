<script setup>
import { ref } from 'vue';
import logo from './assets/HelpStud.png';
import sideImage from './assets/cfu.png';
import searchIcon from './assets/search-icon.png'; // Импортируем иконку поиска

const searchQuery = ref('');
</script>

<template>
  <div class="page-container">
    <div class="header">
      <img :src="logo" alt="HelpStud Logo" class="logo" />
      <h1 class="title">HelpStud</h1>
      <div class="search-container">
        <div class="search-input-wrapper">
          <img :src="searchIcon" alt="Search" class="search-icon" />
          <input
            v-model="searchQuery"
            type="text"
            placeholder="Поиск предмета..."
            class="search-input"
          />
        </div>
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

    <!-- Футер -->
    <footer class="footer">
      <div class="footer-bottom">
        <p>&copy; 2023 HelpStud. Все права защищены.</p>
        <p>
          Разработано <a href="https://github.com/Metelykx" target="_blank" class="metelykx-link">Metelykx</a>
        </p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Основной контейнер страницы */
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh; /* Минимальная высота на весь экран */
}

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

.search-input-wrapper {
  display: flex;
  align-items: center;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 25px;
  padding: 8px 15px;
  transition: background-color 0.3s, box-shadow 0.3s;
}

.search-input-wrapper:hover {
  background-color: rgba(255, 255, 255, 0.2);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.search-icon {
  width: 20px;
  height: 20px;
  margin-right: 10px;
  filter: brightness(0) invert(1); /* Делаем иконку белой */
}

.search-input {
  flex: 1;
  background: transparent;
  border: none;
  outline: none;
  color: #ffffff;
  font-size: 16px;
  font-family: 'Kanit', sans-serif;
}

.search-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.content {
  flex: 1; /* Растягиваем контент на всё доступное пространство */
  padding-top: 12%; /* Отступ для хедера */
  width: 100%;
  box-sizing: border-box;
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

/* Стили для футера */
.footer {
  background-color: transparent; /* Убираем синий фон */
  color: #333; /* Темный цвет текста */
  padding: 10px 20px; /* Уменьшаем отступы */
  font-family: 'Kanit', sans-serif;
  margin-top: auto; /* Прижимаем футер к низу */
  text-align: center; /* Центрируем текст */
  border-top: 1px solid #e0e0e0; /* Добавляем тонкую линию сверху */
}

.footer-bottom {
  display: flex;
  flex-direction: column;
  gap: 5px; /* Расстояние между строками */
}

.footer-bottom p {
  margin: 0;
  font-size: 12px; /* Уменьшаем размер текста */
  color: #666; /* Серый цвет текста */
}

.metelykx-link {
  color: #007bff; /* Синий цвет ссылки */
  text-decoration: none; /* Убираем подчеркивание */
  transition: color 0.3s;
}

.metelykx-link:hover {
  color: #0056b3; /* Темно-синий цвет при наведении */
  text-decoration: underline; /* Подчеркивание при наведении */
}
</style>