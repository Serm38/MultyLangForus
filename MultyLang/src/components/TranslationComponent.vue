<template>
  <div>
    <input type="text" v-model="inputText" placeholder="Введите текст" />
    <button @click="translateText">Перевести</button>
    <p>Результат: {{ translatedText }}</p>
  </div>
</template>

<script>

import { createI18n } from 'vue-i18n';
  
const i18n = createI18n({
  legacy: false,
  locale: 'ru',
  messages: {
    ru: {
      greeting: 'Привет, мир!',
    },
    en: {
      greeting: 'Hello, world!',
    },
  },
});

export default {
  data() {
    return {
      inputText: '',
      translatedText: '',
    };
  },
  methods: {
    translateText() {
      if (i18n.global.locale === 'ru') {
        this.translatedText = i18n.global.t('en.greeting');
      } else {
        this.translatedText = i18n.global.t('ru.greeting');
      }
    },
  },
};
</script>