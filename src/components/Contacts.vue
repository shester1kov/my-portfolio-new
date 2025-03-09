<template>
    <section class="contacts">
      <h2>Контакты</h2>
      <p>Свяжитесь со мной:</p>
      <ul>
        <li>📧 Email: <a href="mailto:example@email.com">example@email.com</a></li>
        
        <li>🐙 GitHub: <a href="https://github.com/shester1kov" target="_blank">github.com/shester1kov</a></li>
      </ul>
  
      <form @submit.prevent="sendMessage">
        <input type="text" v-model="name" placeholder="Ваше имя" required />
        <input type="email" v-model="email" placeholder="Ваш email" required />
        <textarea v-model="message" placeholder="Ваше сообщение" required></textarea>
        <button type="submit">Отправить</button>
      </form>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: "",
        email: "",
        message: ""
      };
    },
    methods: {
      sendMessage() {
        alert(`Сообщение от ${this.name} (${this.email}): ${this.message}`);
        this.name = "";
        this.email = "";
        this.message = "";
      }
    }
  };
  </script>
  
  <style scoped>
  .contacts {
    padding: 20px;
    text-align: center;
  }
  
  .contacts ul {
    list-style: none;
    padding: 0;
  }
  
  .contacts li {
    margin: 10px 0;
  }
  
  .contacts a {
    color: #1d4e89;
    text-decoration: none;
    font-weight: bold;
  }
  
  .contacts a:hover {
    text-decoration: underline;
  }
  
  form {
    margin-top: 20px;
    display: flex;
    flex-direction: column;
    gap: 10px;
    max-width: 300px;
    margin-left: auto;
    margin-right: auto;
  }
  
  input, textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  button {
    background: #1d4e89;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
    font-weight: bold;
  }
  
  button:hover {
    background: #0f1b33;
  }
  </style>
  