<template>
    <section class="projects">
      <h2>Мои проекты</h2>
      <div class="projects-list">
        <div v-for="project in projects" :key="project.id" class="project-card">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          <a :href="project.link" target="_blank">Подробнее</a>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        projects: [
          { id: 1, title: "API интернет-магазина", description: "Бэкенд на Go.", link: "https://github.com/shester1kov/myproject" },
          { id: 2, title: "API интернет-магазина", description: "Бэкенд на Python с использованием FastAPI.", link: "https://github.com/shester1kov/fastapi_ecommerce" },
          { id: 3, title: "Заметки", description: "Сервис для создания заметок с MongoDB и Redis.", link: "https://github.com/shester1kov/notes_project" }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  .projects {
    padding: 20px;
    text-align: center;
  }
  
  .projects-list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
  }
  
  .project-card {
    background: #fff;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    width: 250px;
  }
  
  .project-card h3 {
    margin: 10px 0;
  }
  
  .project-card a {
    display: inline-block;
    margin-top: 10px;
    color: #1d4e89;
    text-decoration: none;
    font-weight: bold;
  }
  
  .project-card a:hover {
    text-decoration: underline;
  }
  </style>
  