<script setup lang="ts">
import { ref, watch } from 'vue'
import ChildComponent from './components/ChildComponent.vue'

const textValue = ref('')
const selectedValue = ref('option1')

watch(textValue, (newValue, oldValue) => {
    console.log(`Le texte est passé de ${oldValue} à ${newValue}`)
})

watch(selectedValue, (newValue, oldValue) => {
    console.log(`L'option sélectionnée est passée de ${oldValue} à ${newValue}`)
})
</script>

<template>
  <div class="container">
    <h2>Communication Parent-Enfant avec v-model</h2>
    <p>Texte dans le parent: {{ textValue }}</p>
    <p>Option sélectionnée dans le parent: {{ selectedValue }}</p>
    <ChildComponent v-model:textValue="textValue" v-model:selectedValue="selectedValue" />
  </div>
</template>

<style scoped> </style>
