<script setup lang="ts">
import { ref } from 'vue';

const count = ref<number>(0)
</script>

<template>
<article class="card">
  <img src="/assets/posts/vuepress/grandma-computer.png" alt="Anthony">
  <p class="name">Développeur Senior</p>
  <p class="price">1 appel (40 min) / jour</p>
  <div class="actions">
    <button aria-label="remove 1" @click="count--" :disabled="count===0">-</button>
    <span class="count">{{ count }}</span>
    <button aria-label="add 1" @click="count++">+</button>
  </div>
</article>
</template>

<style scoped>
.card {
  background-color: hsl(240deg 7% 20%);
  padding: 1em;
  border-radius: 2px;
  width: 200px;
}

.name {
  margin-block: .5em;
}

.price {
  font-weight: bold;
  font-size: 0.8em;
  margin-block: .5em;
}
.price::before {
  content: "prix: ";
}

.actions {
  margin-inline: auto;
  margin-block-start: 1em;
  width: fit-content;
}

.count {
  margin-inline: 1em;
}
</style>