<script setup lang="ts">
import Button from './components/Button.vue';

import { ref } from 'vue';

const counter = ref<number>(0)

const incremet = () => {
  counter.value++
}

const decrement = () => {
  counter.value--
}

</script>

<template>

  <main class="Page">

    <div class="Page__Content">

      <p class="Content__Number">
        {{counter}}
      </p>

      <div class="Content__ButtonContainer">

        <Button color="red" @click="decrement"> Отнять </Button>
        <Button color="green" @click="incremet"> Добавить </Button>

      </div>

    </div>

  </main>
  
</template>

<style scoped>
.Page{
  display: flex;
  flex-direction: column;

  width: 100vw;
  height: 100vh;
}
.Page__Content{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  width: 100%;
  height: 100%;
}
.Content__Number{
  font-size: 6em;

  font-weight: bold;

  display: flex;
  align-items: center;
  justify-content: center;
}
.Content__ButtonContainer{
  margin-top: 5%;

  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;

  gap: 5%;

  min-width: 300px;
  min-height: 60px;
}
</style>
