<template>
    <header :class="{ dark: isDarkMode }" class="header">
      <h1 class="logo">Мой сайт</h1>
      <nav>
      <a href="#" @click.prevent="$emit('change-section', 'profile')">Обо мне</a>
      <a href="#" @click.prevent="$emit('change-section', 'projects')">Проекты</a>
      <a href="#" @click.prevent="$emit('change-section', 'contacts')">Контакты</a>
    </nav>
      <button class="theme-toggle" @click="$emit('toggle-theme')">
        <span v-if="isDarkMode">☀ Светлая тема</span>
      <span v-else>🌙 Темная тема</span>
      </button>
    </header>
  </template>

  <script>
  export default {
    props: ["isDarkMode"]
  }
</script>
  
  
<style scoped>

nav a {
    margin: 0 10px;
    color: white;
    text-decoration: none;
    font-weight: bold;
  }
  nav a:hover {
    text-decoration: underline;
  }

.header,
.dark {
  transition: background-color 0.5s ease, color 0.5s ease;
}

/* шапка */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #1d4e89;
  color: white;
  padding: 15px;
}

/* тёмная тема */
.dark {
  background: #0f1b33;
  color: white;
}

/* плавная смена фона страницы */
.dark body {
  background-color: #121212;
  color: white;
  transition: background-color 0.5s ease, color 0.5s ease;
}

/* плавный эффект для кнопки */
.theme-toggle {
  padding: 8px 15px;
  border: none;
  cursor: pointer;
  font-size: 14px;
  font-weight: bold;
  border-radius: 20px;
  background: linear-gradient(45deg, #ffa500, #ff4500);
  color: white;
  transition: transform 0.3s ease, filter 0.3s ease, background-color 0.5s ease;
  display: flex;
  align-items: center;
  gap: 5px;
}

/* эффект при наведении */
.theme-toggle:hover {
  filter: brightness(1.2);
  transform: scale(1.05);
}

/* эффект при нажатии */
.theme-toggle:active {
  transform: scale(0.95);
}
</style>
