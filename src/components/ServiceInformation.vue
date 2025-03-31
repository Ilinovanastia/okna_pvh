<template>
<div class="base-component main" id="services">
  <div class= 'head'>
    <h1>Наши услуги</h1>
  </div>
  <div class = 'service'>
    <div class="service-card-1">
      <div class="service-item-content">
        <div class="text-content">
          <h3 class="service-card-title">Установка пластиковых окон</h3>
          <p class="service-card-description">Краткое описание услуги.</p>
          <div class="service-card-price">от 100$</div>
        </div>
        <div class="service-card-icon">
            <img src="service/photo_1.webp" alt="Иконка услуги">
        </div>
      </div>
    </div>
    <div class="service-card-2">
      <div class="service-item-content">
          <div class="text-content">
            <h3 class="service-card-title">Остекление балконов и лоджий</h3>
            <p class="service-card-description">Краткое описание услуги.</p>
            <div class="service-card-price">от 100$</div>
          </div>
          <div class="service-card-icon">
              <img src="service/photo_2.png" alt="Иконка услуги">
          </div>
      </div>
    </div>
    <div class="service-card-3">
      <div class="service-item-content">
          <div class="text-content">
            <h3 class="service-card-title">Остекление коттеджей и дач</h3>
            <p class="service-card-description">Краткое описание услуги.</p>
            <div class="service-card-price">от 100$</div>
          </div>
          <div class="service-card-icon">
              <img src="service/photo_3.png" alt="Иконка услуги">
          </div>
      </div>
    </div>
    <div class="service-card-4">
      <div class="service-item-content">
          <div class="text-content">
            <h3 class="service-card-title">Остекление корпоративных объектов</h3>
            <p class="service-card-description">Краткое описание услуги.</p>
            <div class="service-card-price">от 100$</div>
          </div>
          <div class="service-card-icon">
              <img src="service/photo_4.jpg" alt="Иконка услуги">
          </div>
      </div>
    </div>
  </div>
</div>
</template>

<style scoped>
.main {
  display: flex;
  flex-direction: column;
  padding-bottom: 3%;
  padding-top: 2%;
}
.head {
  display: flex;
  justify-content: center;
  margin-bottom: 2%;
  margin-top: 0%;
}
.service {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.service-card-1,
.service-card-2,
.service-card-3,
.service-card-4 {
  position: relative;
  border: 1.5px solid #ffffff;
  flex: 0 0 calc(50% - 35px);
  margin: 15px;
  border-radius: 8px;
  overflow: hidden;
  background-color: #000000;
  height: 230px;
  transform: scale(0.95);
  transition: transform 0.3s ease-in-out;
}
.service-card-1:hover,
.service-card-2:hover,
.service-card-3:hover,
.service-card-4:hover {
  transform: scale(1);
}
.service-card-1::before,
.service-card-2::before,
.service-card-3::before,
.service-card-4::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
  z-index: -1;
  border-radius: inherit;
}
.service-card-1:hover::before,
.service-card-2:hover::before,
.service-card-3:hover::before,
.service-card-4:hover::before {
  opacity: 0.4;
}
.service-card-1::before,
.service-card-3::before {
  background-color: #4bb462;
}
.service-card-2::before,
.service-card-4::before {
  background-color: #a771fe;
}
.service-card-icon {
  max-width: 350px;
  max-height: 380px;
  padding: 0;
  opacity: 0.8;
  transition: opacity 0.7s ease;
}
.service-card-icon:hover {
  opacity: 1;
}
.service-card-icon img {
  max-width: 100%;
  max-height: 100%;
}
.service-item-content {
  padding-left: 20px;
  display: flex;
  justify-content: space-between;
}
.service-card-title {
  margin-bottom: 5px;
}
.service-card-description {
  margin-bottom: 5px;
  line-height: 1.4;
}
.service-card-price {
  font-weight: bold;
  margin-top: auto;
}
</style>