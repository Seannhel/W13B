
<template>
  <article class="tweet" :class="layout">
    <div class="user">
      <div class="avatar">👤</div>

      <div>
        <h3>{{ tweet.user }}</h3>
        <span>{{ tweet.handle }}</span>
      </div>
    </div>

    <p class="content">{{ tweet.content }}</p>

    <div class="bottom">
      <span class="date">📅 {{ tweet.date }}</span>
      <span class="icons">♡ ↗</span>
    </div>
  </article>
</template>

<script>
export default {
  name: "TweetItem",
  props: {
    tweet: {
      type: Object,
      required: true,
    },
    layout: {
      type: String,
      default: "grid",
    },
  },
};
</script>

<style scoped>
.tweet {
  background: #1e293b;
  border: 1px solid #334155;
  border-radius: 12px;
  padding: 25px;
  text-align: left;
  transition: 0.2s;
}

.tweet:hover {
  border-color: #818cf8;
}

.user {
  display: flex;
  align-items: center;
  gap: 12px;
}

.avatar {
  background: #3730a3;
  border-radius: 50%;
  width: 45px;
  height: 45px;
  display: grid;
  place-items: center;
}

h3 {
  margin: 0 0 5px;
  font-size: 17px;
}

span {
  color: #94a3b8;
  font-size: 13px;
}

.content {
  line-height: 1.6;
  margin: 20px 0;
}

.bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  padding-top: 12px;
  border-top: 1px solid #334155;
}

.date {
  color: #cbd5e1;
  font-size: 13px;
}

.icons {
  color: #a5b4fc;
  font-size: 16px;
}

.list {
  border-left: 4px solid #6366f1;
}
</style>
