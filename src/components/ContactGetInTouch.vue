<template>
    <div class = 'contacts base-component' id="contacts"> 
       <h1>Контакты</h1>
       <div class = 'text'>Бесплатная консультация</div>
       <div class = 'number'><span v-if="isMobile">
      <a :href="'tel:' + phoneNumber" class="phone-link">
        {{ phoneNumber }}
      </a>
    </span>
    <span v-else>
      {{ phoneNumber }}
    </span></div>
       <div class = 'mail'><a :href="'mailto:' + email">{{ email }}</a></div>
       <div class = 'adress'>Воронеж, ул. 9 января, 150</div>
    </div>
</template>

<script setup>

import { ref, onMounted, onBeforeUnmount } from 'vue';

const email = ref('igv6767@mail.ru');
const phoneNumber = ref('+7 (952) 956-20-15'); // Замени на свой номер телефона
const isMobile = ref(false);

const checkIsMobile = () => {
    isMobile.value = window.innerWidth <= 768; // Например, 768px - это типичный breakpoint для мобильных устройств
  };

onMounted(() => {

  checkIsMobile(); // Проверяем при монтировании компонента

  window.addEventListener('resize', checkIsMobile); // Проверяем при изменении размера окна
});

onBeforeUnmount(() => {
  window.removeEventListener('resize', checkIsMobile);
});

</script>

<style scoped>
.contacts {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding-bottom: 3%;
}
.contacts div{
    padding-bottom: 5px;
}
.mail a{
    color: #ffffff;
    text-decoration: none;
}
.mail a:hover {
    color: #4bb462
}
</style>