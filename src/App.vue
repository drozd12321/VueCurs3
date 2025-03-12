<script setup></script>

<template>
  <form action="">
    <h1>Анкета для Vue</h1>
    <div class="formgr">
      <label for="name"><strong>Имя:&nbsp;</strong> </label>
      <input id="name" type="text" />
    </div>
    <div class="formgr">
      <label for="age"><strong>Возраст:&nbsp;</strong> </label>
      <input id="age" type="text" />
    </div>
    <div class="formgr">
      <label for="city"><strong>Город:&nbsp;</strong> </label>
      <select id="city" type="text">
        <option value="">Орел</option>
        <option value="">Новгород</option>
        <option value="">Питер</option>
      </select>
    </div>
    <div>
      <p>Готов к поедке?</p>
    </div>
  </form>
</template>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  margin: auto;
  width: 95%;
  height: 500px;
  background-color: #333;
  color: #fff;
  padding: 10px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  align-items: center;
}
form h1 {
  text-align: center;
}
input {
  width: 500px;
  border-radius: 5px;
  outline: none;
  border: none;
  padding: 5px;
}
select {
  width: 500px;
  border-radius: 5px;
  outline: none;
  border: none;
  padding: 5px;
  color: black;
  font-weight: 500;
}
.formgr {
  display: flex;
  align-self: center;
  align-items: center;
  margin-bottom: 20px;
  width: 500px;
}
</style>
