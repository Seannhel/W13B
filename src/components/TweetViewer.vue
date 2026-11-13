
<template>
  <section>
    <div class="toolbar">
      <h3>Latest Tweets</h3>

      <button @click="isGrid = !isGrid">
        {{ isGrid ? "☰ List View" : "▦ Card View" }}
      </button>
    </div>

    <div class="tweets" :class="isGrid ? 'grid' : 'list'">
      <TweetItem
        v-for="tweet in tweets"
        :key="tweet.id"
        :tweet="tweet"
        :layout="isGrid ? 'grid' : 'list'"
      />
    </div>
  </section>
</template>

<script>
import TweetItem from "./TweetItem.vue";

export default {
  name: "TweetViewer",
  components: {
    TweetItem,
  },
  props: {
    tweets: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      isGrid: true,
    };
  },
};
</script>

<style scoped>
.toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 25px;
}

button {
  background: #6366f1;
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #4f46e5;
}

.tweets {
  display: grid;
  gap: 20px;
}

.grid {
  grid-template-columns: repeat(2, 1fr);
}

.list {
  grid-template-columns: 1fr;
}

@media (max-width: 600px) {
  .grid {
    grid-template-columns: 1fr;
  }
}
</style>
