
<script setup>
import { ref, computed } from 'vue';

const cards = {
  1: { title: 'Окна ООО"Стандарт"', description1: 'Мы работаем на рынке более 17 лет', description2: 'У нас квалифицированные замерщики, которые прошли обучение и имеют стаж работы от 5 лет', description3: 'Мы знаем, что качественный монтаж 100% влияет на шумо, тепло и пылеизоляцию' },
  2: { title: 'Окна ООО"Стандарт"', description1: 'Выполняем замеры, доставку, монтаж и уборку помещения', description2: 'Работы по установке пластиковых окон выполняются монтажниками с минимальным опытом работы в 3 года', description3: 'Монтаж пластиковых окон занимает до 7 часов, после чего происходит уборка строительного мусора'},
};
const selectedCategory = ref(null); 
const selectCategory = (categoryId) => {
  selectedCategory.value = categoryId;
}; 
const currentCard = computed(() => {
  return cards[selectedCategory.value] || {};
});

</script>

<template>
  <div class="card-selector base-component" id="about">
       <h1>О компании</h1>
      <div class="button-group">
        <button @click="selectCategory(1)" :class="{ active: selectedCategory === 1 || !selectedCategory}">Описание</button>
        <button @click="selectCategory(2)" :class="{ active: selectedCategory === 2 }">Как мы работаем</button>
        <button @click="selectCategory(3)" :class="{ active: selectedCategory === 3 }">Сертификаты</button>
      </div>
      <div v-if="selectedCategory && selectedCategory != 3" class="card-container">
          <div class="card info-1">
            <div class = 'object-info-1'>
              <p>{{ currentCard.description1 }}</p>
            </div>
            <div class = 'object-info-2'>
              <p>{{ currentCard.description2 }}</p>
            </div>
            <div class = 'object-info-3'>
              <p>{{ currentCard.description3 }}</p>
            </div>
          </div>
      </div>
      <div v-if="!selectedCategory" class="card-container">
          <div class="card info-2">
              <div class = 'object-info-1'>
                <p>{{ cards[1].description1 }}</p>
              </div>
              <div class = 'object-info-2'>
                <p>{{ cards[1].description2 }}</p>
              </div>
              <div class = 'object-info-3'>
                <p>{{ cards[1].description3 }}</p>
              </div>
          </div>
      </div>
      <div v-if="selectedCategory===3" class="card-container">
          <div class="card">
              <div v-for = "i in 8" :key="i" class="card-image">
                <img :src="`certificates/sertificat${i}.jpg`" alt="Изображение" >
              </div>
          </div>
      </div>
  </div>
</template>

<style>
h1 {
  margin-bottom: 2%;
}
.card-selector {
  display: flex;
  flex-direction: column;
  text-align: center;
  height: auto; /* Автоматическая высота */
  padding-bottom: 5%; /* Уменьшил отступ снизу */
}
.button-group {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
  flex-wrap: wrap;
}

.button-group button {
  padding: 12px 20px;  /* Уменьшил отступы в кнопках */
  border-radius: 5px;
  margin: 5px;
  cursor: pointer;
  background-color: #000;
  color: #fff;
  border-color: transparent;
  transition: background-color 0.3s, color 0.3s;
  font-size: 0.9em;  /* Уменьшил размер шрифта */
}

.button-group button.active {
  background-color: #fff;
  font-weight: bold;
  color: #000
}
.card-container {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 1%;
}
.card {
  width: 80%;
  padding: 4%;
  display: flex;
  flex-direction: wrap;
}
.card .object-info-1, .card .object-info-2, .card .object-info-3 {
  margin: 1.5%;
  padding: 1%;
  border-radius: 15px;
  height: 300px;
  width: 680px;
  display: flex;
  align-items: center;
  font-size: 1.4em;
}
.object-info-1 {
  background-color: #FFF;
  color: #000;
}
.object-info-2 {
  background-color: #4bb462;
}
.object-info-3 {
  background-color: #a771fe;
}
.card-image img{
    max-width: 90%;
    max-height: 800px;
    object-fit: contain;
}
@media (min-width: 768px) and (max-width: 992px) {
  .card .object-info-1, .card .object-info-2 {
        width: auto !important;
        height: auto !important;
  }
}
@media (max-width: 768px) {
  .card .object-info-1, .card .object-info-2, .card .object-info-3 {
        width: auto !important;
        height: auto !important;
  }
}
</style>
