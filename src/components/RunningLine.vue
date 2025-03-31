<template>
 <div class="marquee-container">
    <div class="marquee-content">
      <span>ЭТО ОКНА ООО СТАНДАРТ.       ЭТО ОКНА ООО СТАНДАРТ.      ЭТО ОКНА ООО СТАНДАРТ.      ЭТО ОКНА ООО СТАНДАРТ </span>
    </div>
 </div>
</template>

<style scoped>
.marquee-container {
  font-size: 55px;
  font-weight: bold;
  color: #000;
  width: 100%;
  overflow: hidden;
  white-space: nowrap;
  margin-bottom: 5%;
}
.marquee-content {
  display: inline-block;
  padding-left: 100%;
  animation: marquee 25s linear infinite;
}
@keyframes marquee {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-100%);
  }
}
</style>
