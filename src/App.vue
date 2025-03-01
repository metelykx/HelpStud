<script setup>
import { ref } from 'vue';
import logo from './assets/HelpStud.png';
import sideImage from './assets/cfu.png';
import searchIcon from './assets/search-icon.png';

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
              Университет — это важный шаг во взрослую жизнь, где ты найдёшь друзей, знания и начнёшь строить своё будущее.
            </p>
            <p class="subjects">
              HelpStud создан, чтобы помочь тебе в обучении по направлениям: <b>Программная инженерия, Информатика и вычислительная техника, Компьютерная безопасность и другим.</b>
            </p>
            <p>
              Используй <strong>поисковик</strong>, чтобы найти советы, ответы на вопросы и учебные материалы по нужному предмету. <b>Просто введи название — и получи результат!</b>
            </p>
            <p>
              Начни учиться уже сейчас и достигай своих целей быстрее!
            </p>
            <p>
              Развивайся и учись вместе с <b>HelpStud</b>!
            </p>
          </div>
          <img :src="sideImage" alt="CFU Image" class="side-image" />
        </div>
      </div>
    </div>

    <!-- Футер -->
    <footer class="footer">
      <div class="footer-content">
        <div class="footer-section">
          <h3 class="footer-heading">Связь с нами</h3>
          <ul class="contact-list">
            <li>
              <a href="https://t.me/helpstud" target="_blank" class="contact-link">Telegram</a>
            </li>
          </ul>
        </div>
        <div class="footer-section right-section">
          <p>&copy; 2025 HelpStud.</p>
          <p>
            Разработано <a href="https://github.com/Metelykx" target="_blank" class="metelykx-link" id="links">Metelykx</a>
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Основной контейнер страницы */
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Делаем текст внутри <b> жирным */
b {
  font-weight: bold;
}

/* Хедер */
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
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out forwards;
}

.logo {
  width: 50px;
  height: auto;
  margin-right: 15px;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.2s forwards;
}

.title {
  font-size: 25px;
  font-weight: bold;
  color: #ffffff;
  font-family: 'Kanit', sans-serif;
  margin-right: auto;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.3s forwards;
}

.search-container {
  margin-left: 20px;
  width: 300px;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.4s forwards;
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
  filter: brightness(0) invert(1);
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

.search-input:focus {
  border-color: #ffffff;
  background-color: rgba(255, 255, 255, 0.2);
}

/* Основной контент */
.content {
  flex: 1;
  padding-top: 10%;
  width: 100%;
  box-sizing: border-box;
}

.str {
  font-family: 'Kanit', sans-serif;
  color: #ffffff;
  line-height: 1.6;
  width: 100%;
  max-width: 1200px;
  padding: 30px;
  font-size: 20px;
  text-align: justify;
  margin: 20px auto 40px;
  border-radius: 20px;
  background: rgba(30, 30, 30, 0.6); /* Увеличена непрозрачность чёрного фона */
  backdrop-filter: blur(12px); /* Усилено размытие */
  border: 1px solid rgba(255, 255, 255, 0.3); /* Более яркая рамка */
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3); /* Усиленная тень */
  margin-left: 2.7%;
  opacity: 0; /* Начальное состояние */
  animation: fadeIn 0.5s ease-in-out 0.4s forwards; /* Анимация */
}

.about-heading {
  font-size: 30px;
  font-weight: bold;
  color: #007bff;
  font-family: 'Kanit', sans-serif;
  margin: 20px 0;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.5s forwards;
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
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.6s forwards;
}

.side-image {
  width: 400px;
  height: auto;
  margin-top: 0;
  flex-shrink: 0;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.7s forwards;
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

/* Анимация для плавного появления */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Футер */
.footer {
  background-color: transparent;
  color: #7d7d7d;
  padding: 8px 20px;
  font-family: 'Kanit', sans-serif;
  margin-top: auto;
  text-align: center;
  border-top: 1px solid #8b8b8b;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.8s forwards;
  margin-left: 2.7%;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: 1200px;
  margin-bottom: 8px;
  gap: 10px;
}

.footer-section {
  flex: 1;
  margin: 0;
}

.footer-heading {
  font-size: 15px;
  font-weight: bold;
  color: #007bff;
}

.contact-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.contact-list li {
  margin-bottom: 4px;
}

.contact-link,
.metelykx-link {
  color: #7d7d7d;
  text-decoration: none;
  transition: color 0.3s;
  font-size: 15px;
}

.contact-link:hover,
.metelykx-link:hover {
  color: #007bff;
  text-decoration: underline;
}
#links {
  color: #007bff;
}
</style>