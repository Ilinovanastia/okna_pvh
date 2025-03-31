<script setup>
import MainSectionView from '@/components/MainSection.vue';
import NavigationMenuView from '@/components/NavigationMenu.vue';
</script>

<template>
    <div class="base-component" id="main">
        <NavigationMenuView/>
        <div class="component-content-heading">
              <h2>Окна стандарт -  Надежное решение для остекления</h2>
              <p>Компания ООО СТАНДАРТ с 2004 года производит и продает пластиковые окна в Воронеже и Воронежской области.<br> Нам удалось достичь профессионального уровня в монтаже оконных конструкций.</p>
        </div>
        <div class = 'MainSection'>
        <MainSectionView/>
        </div>
    </div>
</template>

<style scoped>
.base-component {
    padding-bottom: 2%;
}
.component-content-heading {
    padding: 70px;
}
.component-content-heading h2 {
    font-size: 36px;
    text-align: center;
    margin-bottom: 60px;
    transition: font-size 2s;
    min-height: 48px;
    line-height: 48px;
    animation: increaseFontSize 2s forwards;
}
@keyframes increaseFontSize {
    from {
        font-size: 36px;
    }
    to {
        font-size: 45px;
    }
}
.component-content-heading p {
    text-align: center;
}
.MainSection {
    display: flex;
    justify-content: center;
    align-items: end;
}
</style>