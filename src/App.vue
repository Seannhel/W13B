
<template>
  <div id="app">
    <header>
      <h1>✦ PostSwitch</h1>
      <p>Vue.js Tweet Viewer</p>
    </header>

    <main>
      <h2>Welcome to PostSwitch</h2>
      <p class="subtitle">Explore tweets in your favorite layout.</p>

      <TweetViewer :tweets="tweets" />
    </main>
  </div>
</template>

<script>
import TweetViewer from "./components/TweetViewer.vue";

export default {
  name: "App",
  components: {
    TweetViewer,
  },
  data() {
    return {
      tweets: [
        {
          id: 1,
          user: "Skyline Hub",
          handle: "@skylinehub",
          content: "Exploring destinations with Vue.js! ✈️",
          date: "Nov 12, 2026",
        },
        {
          id: 2,
          user: "Code Developer",
          handle: "@codedev",
          content: "Learning Vue components is awesome! 💻",
          date: "Nov 11, 2026",
        },
        {
          id: 3,
          user: "Tech Daily",
          handle: "@techdaily",
          content: "Switch between card and list views!",
          date: "Nov 10, 2026",
        },
      ],
    };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: #0f172a;
  color: white;
  font-family: Arial, sans-serif;
}

header {
  background: #1e293b;
  padding: 20px 8%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h1 {
  color: #a5b4fc;
}

main {
  max-width: 1000px;
  margin: auto;
  padding: 50px 20px;
  text-align: center;
}

.subtitle {
  color: #94a3b8;
  margin-bottom: 40px;
}
</style>
