<template>
    <div class="profile">
      <img src="../assets/images.jpg" alt="Аватар" class="avatar" />
      <h1>{{ name }}</h1>
      <p>{{ bio }}</p>

  
      <div class="links">
        <a v-for="link in links" :key="link.url" :href="link.url" target="_blank">
          {{ link.text }}
        </a>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: "Дима",
        bio: "Описание.",
        links: [
          { text: "GitHub", url: "https://github.com/shester1kov" },
        ],
      };
    },

  };
  </script>
  
  <style scoped>

  .profile {
    text-align: center;
    padding: 20px;
    width: 400px;
    max-width: 400px;
    margin: 50px auto;
    background: white;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
  }
  .profile:hover {
    transform: scale(1.02);
  }
  
  .avatar {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    border: 3px solid #1d4e89;
  }

  .btn {
    background: #ff4500;
    color: white;
    border: none;
    padding: 10px 15px;
    margin: 10px 0;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s;
  }
  .btn:hover {
    background: #d43d00;
  }

  .links a {
    display: inline-block;
    margin: 10px;
    padding: 10px 15px;
    background: #1d4e89;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    transition: background 0.3s;
  }
  .links a:hover {
    background: #0f1b33;
  }
  
  @media (max-width: 480px) {
    .profile {
      width: 90%;
      padding: 15px;
    }
    .avatar {
      width: 100px;
      height: 100px;
    }
    .btn {
      width: 100%;
    }
  }
  </style>
  