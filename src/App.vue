<script setup>
import { ref } from 'vue'; // Импортируем ref из Vue
import logo from './assets/HelpStud.png'; // Проверь, что путь к картинке правильный

// Состояние для поискового запроса (пока не используется)
const searchQuery = ref('');
</script>

<template>
  <div class="header">
    <img :src="logo" alt="HelpStud Logo" class="logo" />
    <h1 class="title">HelpStud</h1>
    <!-- Поисковик в хедере -->
    <div class="search-container">
      <input
        v-model="searchQuery"
        type="text"
        placeholder="Поиск предмета..."
        class="search-input"
      />
    </div>
  </div>

  <!-- Основной контент -->
  <div class="content">
    <div class="str">
      <p>
        Университет — это важный шаг во взрослую жизнь, 
        где ты не только встретишь новых друзей, которые останутся с тобой на протяжении многих лет,
        но и найдёшь любовь, способную вдохновить на саморазвитие в стремительном темпе. 
        Кроме того, университет подарит тебе знания, которые станут основой твоего будущего.
      </p>
      <p>
        Именно для этого существует HelpStud! Этот сайт поможет тебе в обучении по таким направлениям, как Программная инженерия, 
        Информатика и вычислительная техника, а также Компьютерная безопасность в Крымском Федеральном университете, а может быть не только в нем. 
      </p>
      <p>
        Здесь ты сможешь разобраться в сложных 
        темах различных дисциплин и получить советы по программированию и другим сферам. Чем раньше начнёшь учиться, тем быстрее достигнешь своих целей! 
      </p>
      <p>
        Не упусти возможность развиваться и учиться вместе с HelpStud!
      </p>
    </div>
  </div>
</template>

<style scoped>
/* Хедер фиксирован наверху */
.header {
  display: flex;
  align-items: center; /* Выравниваем элементы по центру по вертикали */
  justify-content: space-between; /* Распределяем элементы по ширине */
  width: 100%;
  height: 80px; /* Высота заголовка */
  position: fixed; /* Фиксируем наверху страницы */
  top: 0;
  left: 0;
  background-color: #007bff; /* Цвет фона хедера */
  padding: 10px 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* Тень для хедера */
  z-index: 1000; /* Чтобы хедер был поверх других элементов */
}

/* Логотип */
.logo {
  width: 50px; /* Настроить размер по желанию */
  height: auto;
  margin-right: 15px; /* Отступ между логотипом и текстом */
}

/* Заголовок */
.title {
  font-size: 25px;
  font-weight: bold;
  color: #ffffff;
  font-family: 'Kanit', sans-serif;
  margin-right: auto; /* Заголовок прижимается к логотипу */
}

/* Контейнер для поисковика */
.search-container {
  margin-left: 20px; /* Отступ от заголовка */
  width: 300px; /* Ширина поисковика */
}

/* Поле ввода для поиска */
.search-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ffffff; /* Белая рамка */
  border-radius: 10px;
  outline: none;
  transition: border-color 0.3s;
  background-color: rgba(255, 255, 255, 0.1); /* Полупрозрачный фон */
  color: #ffffff; /* Белый текст */
}

.search-input::placeholder {
  color: rgba(255, 255, 255, 0.7); /* Полупрозрачный плейсхолдер */
}

.search-input:focus {
  border-color: #ffffff; /* Белая рамка при фокусе */
  background-color: rgba(255, 255, 255, 0.2); /* Светлее фон при фокусе */
}

/* Основной контент */
.content {
  display: flex;
  justify-content: center; /* Центрируем по горизонтали */
  align-items: center; /* Центрируем по вертикали */
  min-height: 100vh; /* Минимальная высота на весь экран */
  padding-top: 80px; /* Отступ сверху, чтобы не перекрывалось хедером */
  box-sizing: border-box; /* Учитываем padding в высоте */
}

/* Блок с текстом */
.str {
  font-family: 'Kanit', sans-serif; /* Шрифт */
  color: #ffffff; /* Цвет текста */
  line-height: 1.6; /* Межстрочный интервал */
  max-width: 800px; /* Ограничение ширины текста */
  padding: 30px; /* Отступы внутри блока */
  font-size: 20px; /* Уменьшаем размер шрифта */
  text-align: justify; /* Выравнивание текста по ширине */
  margin: 0 auto; /* Центрируем блок по горизонтали */
}

.str p {
  margin-bottom: 20px; /* Отступ снизу для каждого абзаца */
  letter-spacing: 0.5px; /* Увеличиваем межбуквенный интервал */
}

.str p:last-child {
  margin-bottom: 0; /* Убираем отступ у последнего абзаца */
}
</style>