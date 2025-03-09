<template>
  <div :class="{ dark: isDarkMode }">
    <SiteHeader :isDarkMode="isDarkMode" @toggle-theme="toggleTheme" @change-section="changeSection"/>
    
    <main>
      <UserProfile v-if="currentSection === 'profile'" />
      <Projects v-if="currentSection === 'projects'" />
      <Contacts v-if="currentSection === 'contacts'" />
    </main>

    <SiteFooter :isDarkMode="isDarkMode" />
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";
import UserProfile from "./components/UserProfile.vue";
import Projects from "./components/Projects.vue";
import Contacts from "./components/Contacts.vue";
import SiteFooter from "./components/SiteFooter.vue";
export default {
  components: {
    SiteHeader,
    UserProfile,
    Projects,
    Contacts,
    SiteFooter,
  },
  data() {
    return {
      isDarkMode: false,
      currentSection: "profile",
    };
  },
  methods: {
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode;
    },
    changeSection(section) {
      this.currentSection = section;
    },
  },
};
</script>

<style>

html, body, #app {
  height: 100vh;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
}

body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 0;
  transition: background-color 0.3s, color 0.3s;
  background-color: #f4f4f4;
  color: #333;
}

main {
  flex-grow: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  min-height: calc(100vh - 250px); /* Учитывает высоту хедера и футера */
}
.dark {
  background-color: #121212;
}


</style>
