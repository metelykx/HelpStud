<script setup>
import { ref, computed } from 'vue';
import logo from './assets/HelpStud.png';
import sideImage from './assets/cfu.png';
import searchIcon from './assets/search-icon.png';

const searchQuery = ref('');
const selectedSubject = ref(null);
const isModalOpen = ref(false); // Состояние модального окна

// Массив предметов
const subjects = [
  { name: "Структуры и алгоритмы обработки данных", description: "Изучение структур данных и алгоритмов их обработки." },
  { name: "Деловая коммуникация и русская речевая культура", description: "Развитие навыков делового общения и культуры речи." },
  { name: "История России", description: "Изучение ключевых событий и процессов в истории России." },
  { name: "Информатика и основы программирования", description: "Основы программирования и работы с информацией." },
  { name: "Высшая математика", description: "Изучение математического анализа, линейной алгебры и других разделов." },
  { name: "Иностранный язык", description: "Изучение иностранного языка для профессионального общения." },
  { name: "Алгоритмизация и программирование", description: "Основы алгоритмизации и программирования." },
  { name: "Физическая культура", description: "Развитие физической подготовки и здорового образа жизни." },
  { name: "Проектная деятельность", description: "Организация и управление проектами." },
  { name: "Операционные системы", description: "Изучение принципов работы операционных систем." },
  { name: "Алгоритмы и методы вычисления", description: "Изучение алгоритмов и методов вычислений." },
  { name: "Современные технологии программирования", description: "Изучение современных подходов и технологий в программировании." },
  { name: "Основы российской государственности", description: "Изучение основ государственного устройства России." },
  { name: "Человек и право", description: "Изучение правовых основ и их применения." },
  { name: "Цифровые технологии в профессиональной сфере", description: "Использование цифровых технологий в профессиональной деятельности." },
  { name: "Цифровая экосистема будущего", description: "Изучение цифровых экосистем и их роли в будущем." },
  { name: "Дискретная математика", description: "Изучение дискретных структур и их свойств." },
  { name: "Математическое и компьютерное моделирование", description: "Изучение методов математического и компьютерного моделирования." },
  { name: "Компьютерные сети", description: "Изучение принципов работы компьютерных сетей." },
  { name: "Теория автоматов и формальных языков", description: "Изучение теории автоматов и формальных языков." },
  { name: "Базы данных", description: "Изучение принципов проектирования и работы с базами данных." },
  { name: "История религий России", description: "Изучение истории религий на территории России." },
  { name: "Объектно-ориентированное программирование", description: "Изучение принципов объектно-ориентированного программирования." },
  { name: "Теория вероятностей и математическая статистика", description: "Изучение теории вероятностей и статистики." },
  { name: "Интеллектуальный анализ данных", description: "Изучение методов анализа данных и машинного обучения." },
  { name: "Основы социального проектирования", description: "Изучение основ создания социальных проектов." },
  { name: "Безопасность природной среды и жизнедеятельности человека", description: "Изучение вопросов экологической безопасности." },
];

// Фильтрация предметов по введённому запросу
const filteredSubjects = computed(() => {
  if (!searchQuery.value) return [];
  return subjects.filter(subject =>
    subject.name.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
});

// Выбор предмета и открытие модального окна
const selectSubject = (subject) => {
  selectedSubject.value = subject;
  isModalOpen.value = true; // Открываем модальное окно
  searchQuery.value = ''; // Очистка поиска
};

// Закрытие модального окна
const closeModal = () => {
  isModalOpen.value = false;
  selectedSubject.value = null; // Очистка выбранного предмета
};
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
        <!-- Список похожих предметов -->
        <div v-if="filteredSubjects.length > 0" class="suggestions">
          <div
            v-for="subject in filteredSubjects"
            :key="subject.name"
            class="suggestion-item"
            @click="selectSubject(subject)"
          >
            {{ subject.name }}
          </div>
        </div>
      </div>
    </div>

    <div class="content">
      <!-- Блок "О нас" -->
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

    <!-- Модальное окно -->
    <div v-if="isModalOpen" class="modal-overlay">
      <div class="modal">
        <button class="close-button" @click="closeModal">×</button>
        <h2>{{ selectedSubject.name }}</h2>
        <p>{{ selectedSubject.description }}</p>
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

<style>
/* Фон всей страницы */
body {
  background: #181818; /* Темный фон для всей страницы */
  margin: 0;
  font-family: 'Kanit', sans-serif;
  color: #ffffff; /* Белый текст по умолчанию */
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
</style>

<style scoped>
/* Основной контейнер страницы */
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background: #181818; /* Темный фон для контейнера */
  color: #ffffff; /* Белый текст по умолчанию */
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
  margin-right: auto;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.3s forwards;
}

/* Поиск */
.search-container {
  position: relative;
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

/* Список предложений */
.suggestions {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  background: #333; /* Темный фон для списка */
  border: 1px solid #444;
  border-radius: 4px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  max-height: 200px;
  overflow-y: auto;
}

.suggestion-item {
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.2s;
  color: #ffffff; /* Белый текст */
}

.suggestion-item:hover {
  background-color: #444; /* Темный фон при наведении */
}

/* Основной контент */
.content {
  flex: 1;
  padding-top: 100px;
  width: 100%;
  box-sizing: border-box;
}

/* Блок "О нас" */
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
  background: #181818; /* Темный фон */
  border: 1px solid rgba(255, 255, 255, 0.3); /* Легкая рамка */
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.4s forwards;
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

/* Модальное окно */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5); /* Затемнение фона */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1001;
}

.modal {
  background: #181818; /* Темный фон для модального окна */
  padding: 20px;
  border-radius: 8px;
  max-width: 500px;
  width: 100%;
  position: relative;
  border: 1px solid rgba(255, 255, 255, 0.3); /* Легкая рамка */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2); /* Тень */
}

.modal h2 {
  color: #007bff; /* Цвет заголовка */
  margin-bottom: 10px;
}

.modal p {
  color: #ffffff; /* Белый текст */
  font-size: 16px;
  line-height: 1.6;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
  color: #007bff; /* Цвет кнопки */
}

.close-button:hover {
  color: #0056b3; /* Цвет кнопки при наведении */
}

/* Футер */
.footer {
  background-color: #181818;
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