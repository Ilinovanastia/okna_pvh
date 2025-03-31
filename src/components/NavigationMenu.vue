<template>
    <nav class="navbar">
        <div class="container">
            <a href="/" class="logo">Логотип</a>
            <ul class="nav-links">
                <li><a href="#main">Главная</a></li>
                <li><a href="#about">О нас</a></li>
                <li><a href="#services">Услуги</a></li>
                <li><a href="#contacts">Контакты</a></li>
            </ul>
            <div class="nav-buttons">
                <button class="button">Заявка на замер</button>
                <button class="button">Заказать расчет</button>
            </div>
        </div>
    </nav>
</template>

<style scoped>
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 10px;
}
.navbar {
    background-color: #000000;
    padding: 15px 0;
    border-radius: 12px;
}
.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.logo {
    color: white;
    font-size: 1.5em;
    font-weight: bold;
    text-decoration: none;
}
.nav-links {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    flex: 1;
}
.nav-links li {
    margin-left: 20px;
}
.nav-links li:first-child {
    margin-left: 0;
}
.nav-links a {
    text-decoration: none;
    color: white;
    transition: color 0.3s;
    padding: 5px 10px;
    border-radius: 3px;
}
.nav-links a:hover {
    color: #4bb462;
    outline: #4bb462 solid 1.5px;
    border-radius: 3px;
    outline-offset: -1.5px;
}
.nav-buttons {
    display: flex;
    align-items: center;
}
.button {
    background-color: #000000;
    border: #fff solid 1.5px;
    color: white;
    padding: 15px 20px;
    border-radius: 4px;
    cursor: pointer;
    margin-left: 10px;
    transition: background-color 0.3s;
}
.button:hover {
    background-color: #a771fe;
}
</style>