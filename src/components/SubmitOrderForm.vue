<script setup>
import MeasuringGuidelineTool from './MeasuringGuidelineTool.vue';
import PaymentOrder from './PaymentOrder.vue';
</script>

<template>
    <div class = 'base-component'>
        <div class="content">
            <div class = 'head'> 
                <h1>Вы можете:</h1>
            </div>
            <div class = 'order'>
                <MeasuringGuidelineTool/>
                <PaymentOrder/>
            </div>
        </div>
        <video
            src="/26_23_08_19.mp4"
            autoplay
            loop
            muted
            playsinline
        ></video>
    </div>
</template>

<style scoped>
.base-component {
    background-color: #fff;
    border: 1.5px solid #000;
    padding-bottom: 5%;
    padding-top: 5%;
    position: relative;
    overflow: hidden;
}
.content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
}
.head {
  display: flex;
  justify-content: center;
  margin-bottom: 2%;
  margin-top: 0%;
}
.order {
  display: flex;
  justify-content: wrap;
}
video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: 1;
}
@media (min-width: 768px) and (max-width: 992px) {
  .order {
        flex-direction: column; /* Компоненты в столбик */
        align-items: center;  /*  Центрируем по горизонтали  */
    }
}
@media (max-width: 768px) {
  .order {
        flex-direction: column; /* Компоненты в столбик */
        align-items: center;  /*  Центрируем по горизонтали  */
      }
}
</style>