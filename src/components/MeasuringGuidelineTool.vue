<template>
    <div class = 'form'>
        <form>
            <h2>Вызвать замерщика на дом</h2>
                <input type = 'text' placeholder = 'ФИО'>
                <input type = 'email' placeholder = 'email'>
                <input type = 'number' placeholder = 'Номер телефона'>
                <input type = 'submit' placeholder = 'Отправить заметку'>
        </form>
    </div>
</template>

<style scoped>
h2 {
    color: #fff;
    margin-bottom: 10%;
    margin-top: 15%;
}
.form {
    border: 1.5px solid #2e4c56;
    border-radius: 12px;
    width: 30%;
    height: 420px;
    margin: auto 150px;
    background-color: #797979;
}
form {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
form input {
    margin-bottom: 4%;
    width: 300px;
    height: 35px;
    background-color: #424242;
    color: #fff;
    border-radius: 5px;
    border-color: transparent;
}
input:focus {
   outline: none;
   box-shadow: none;
}
input[type="submit"] {
  background-color: #6c6c6c;
  width: 230px;
  color: #fff;
  cursor: pointer;
  margin-top: 20px;
}
input[type="submit"]:hover {
  background-color: #2b2b2b;
}
@media (min-width: 768px) and (max-width: 992px) {
  .form {
    width: 500px;
    height: auto;
    margin-bottom: 5%;
  }
}
@media (max-width: 768px) {
    .form {
    width: 400px;
    height: auto;
    margin-bottom: 5%;
  }
}
</style>