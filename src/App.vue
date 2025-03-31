<template>
  <div>
    <MainStandardWindows class="fade" />
    <ServiceInformation class="fade" />
    <RunningLine /> <!-- No fade class -->
    <CompanyDescription class="fade" />
    <PortfolioOurProjects class="fade" />
    <SubmitOrderForm class="fade" />
    <ContactGetInTouch class="fade" />
  </div>
</template>

<script setup>
import MainStandardWindows from '@/components/MainStandardWindows.vue';
import ServiceInformation from '@/components/ServiceInformation.vue';
import PortfolioOurProjects from '@/components/PortfolioOurProjects.vue';
import CompanyDescription from '@/components/CompanyDescription.vue';
import ContactGetInTouch from '@/components/ContactGetInTouch.vue';
import SubmitOrderForm from '@/components/SubmitOrderForm.vue';
import RunningLine from '@/components/RunningLine.vue';

import { onMounted } from 'vue';

onMounted(() => {
  const elements = document.querySelectorAll('.fade');

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  });

  elements.forEach(element => {
    observer.observe(element);
  });
});
</script>

<style scoped>
.fade {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}

.fade.visible {
  opacity: 1;
  transform: translateY(0);
}
.app {
  /*  Убедись, что app занимает всю высоту viewport  */
  min-height: 100vh;
  display: flex;
  flex-direction: column; /*  Чтобы content-container растягивался на всю высоту */
}
</style>

