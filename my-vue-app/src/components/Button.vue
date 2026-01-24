<script setup lang="ts">
import { computed } from 'vue';

type ButtonColor = 'green' | 'red'

const props = defineProps<{
  color?: ButtonColor
}>()

const colorClass = computed(() => props.color ?? 'green')
const baseClass = computed(() => `${colorClass.value}Base`)

const emit = defineEmits<{
  (e: 'click'):void
}>()

</script>

<template>

    <div class="buttonWrapper">

        <button class="button" :class="colorClass" @click="emit('click')">
            <slot></slot>
        </button>

        <div class="baseClass" :class="baseClass"></div>
    </div>
  
</template>

<style scoped>
.buttonWrapper {
  display: inline-block;
  position: relative;
}

.button {
  padding: 10px 20px;

  border-radius: 12px;

  font-size: 1.5em;
  font-weight: bold;
  color: white;

  border: none;
  cursor: pointer;

  position: relative;
  z-index: 2;

  transition: transform 0.1s;
}


.baseClass {
  position: absolute;

  left: 0;
  top: 73%;

  width: 100%;
  height: 17px; 

  border-radius: 0px 0px 12px 12px;

  z-index: 1;

  transition: 0.1s;
}


.green {
  background-color: #28a745;
}
.greenBase {
  background-color: #218838;
}


.red {
  background-color: #dc3545;
}
.redBase {
  background-color: #c82333;
}


.buttonWrapper:hover .button {
  transform: translateY(4.2px);
}
</style>
