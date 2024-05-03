<template>
  <div>
    <h1>Программа перевода текста</h1>
    <TranslationComponent />
  </div>
</template>

<script>
import TranslationComponent from '/src/components/TranslationComponent.vue';

export default {
  components: {
    TranslationComponent,
  },
};
</script>