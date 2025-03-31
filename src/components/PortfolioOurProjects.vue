<template>
  <div class="gallery-container base-component">
    <div class="head">
        <h1>Наши работы</h1>
    </div>
    <div class="portfolio">
        <button class="arrow-button prev" @click="prevImage" :disabled="isPrevDisabled">
          &lt;
        </button>
        <div class="image-slider">
          <div class="image-wrapper" :style="{ transform: `translateX(-${currentIndex * 50}%)` }">
            <div class="slide">
              <img :src="images[0]" alt="Фотография" />
              <img :src="images[1]" alt="Фотография" />
              <img :src="images[2]" alt="Фотография" />
              <img :src="images[3]" alt="Фотография" />
            </div>
            <div class="slide">
              <img :src="images[4]" alt="Фотография" />
              <img :src="images[5]" alt="Фотография" />
              <img :src="images[6]" alt="Фотография" />
              <img :src="images[7]" alt="Фотография" />
            </div>
          </div>
        </div>
        <button class="arrow-button next" @click="nextImage" :disabled="isNextDisabled">
          &gt;
        </button>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const images = ref([
  'portfolio/photo1.jpg', 'portfolio/photo2.jpg', 'portfolio/photo3.jpg', 'portfolio/photo4.jpg',
  'portfolio/photo5.jpg', 'portfolio/photo6.jpg', 'portfolio/photo7.jpg', 'portfolio/photo8.jpg'
]);

const currentIndex = ref(0);

const prevImage = () => {
  if (currentIndex.value > 0) {
    currentIndex.value--;
  }
};

const nextImage = () => {
  if (currentIndex.value < 1) {
    currentIndex.value++;
  }
};

const isPrevDisabled = computed(() => currentIndex.value === 0);
const isNextDisabled = computed(() => currentIndex.value === 1);

</script>

<style scoped>
.gallery-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
  justify-content: center;
}
.portfolio {
  display: flex;
  align-items: center;
  overflow: hidden;
  justify-content: center;
}
.arrow-button {
  background-color: #eee;
  border: none;
  padding: 10px;
  font-size: 40px;
  cursor: pointer;
  border-radius: 6px;
  margin: 0 5px;
  transition: background-color 0.3s;
}
.arrow-button:disabled {
  opacity: 0.5;
  cursor: default;
}
.arrow-button:hover:enabled {
  background-color: #ccc;
}
.image-slider {
  overflow: hidden;
  width: 80%;
}
.image-wrapper {
  display: flex;
  transition: transform 0.5s ease-in-out;
  width: 200%;
}
.slide {
  width: 50%;
  margin-bottom: 2%;
}
.slide img {
  width: 25%;
  height: auto;
  object-fit: cover;
}
</style>