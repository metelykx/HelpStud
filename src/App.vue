<script setup>
import logo from './assets/HelpStud.png'; // Проверь, что путь к картинке правильный
</script>

<template>
  <div class="header">
    <img :src="logo" alt="HelpStud Logo" class="logo" />
    <h1 class="title">HelpStud</h1>
  </div>
</template>

<style scoped>
/* Хедер фиксирован наверху */
.header {
  display: flex;
  align-items: center; /* Выравниваем элементы по центру по вертикали */
  justify-content: center; /* Центрируем содержимое по горизонтали */
  width: 100%;
  height: 80px; /* Высота заголовка */
  position: fixed; /* Фиксируем наверху страницы */
  top: 0;
  left: 0;
  padding: 10px 20px;
}

/* Логотип */
.logo {
  width: 50px; /* Настроить размер по желанию */
  height: auto;
  margin-right: 15px; /* Отступ между логотипом и текстом */
}

/* Текст */
.title {
  font-size: 25px;
  font-weight: bold;
  color: #ffffff;
  font-family: 'Kanit', sans-serif;
}
</style>
