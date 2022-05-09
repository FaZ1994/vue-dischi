<template>
  <div class="card">
    <div class="cardContent">
      <img :src="item.poster" alt="" />
      <div class="textBox">
        <h2>{{ item.title }}</h2>
        <span>{{ item.author }}</span>
        <span>{{ item.year }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppCard",
  props: {
    item: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/vars";

.card {
  background-color: $mainColor;
  height: 350px;
  max-width: 200px;
  padding: 2em;
}

.cardContent {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2em;
  img {
    height: 150px;
    width: 150px;
  }
}

.textBox {
  display: flex;
  align-items: center;
  flex-direction: column;
  max-width: 150px;
  text-align: center;
  h2 {
    color: $titleColor;
    font-size: 1.3em;
    text-transform: uppercase;
    padding-bottom: 0.5em;
  }
  span {
    color: $textColor;
    font-size: 0.8rem;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
}
</style>
