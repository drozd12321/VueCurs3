<script>
import AppInput from "./components/AppInput.vue";

export default {
  data() {
    return {
      nam: "Евгений",
      age: 20,
      city: "vn",
      pereezd: "yes",
      skils: [],
      agree: false,
      errors: {
        name: null,
      },
    };
  },
  methods: {
    formVaid() {
      let valid = false;
      if (this.nam.length < 2) {
        valid = false;
        this.errors.name = "Введите Имя";
        return valid;
      } else {
        this.errors.name = "";
        valid = true;
        return valid;
      }
    },
    handleSubmit() {
      if (this.formVaid()) {
        console.log(
          this.nam,
          this.age,
          this.city,
          this.pereezd,
          this.skils,
          this.agree
        );
      }
    },
  },
  components: {
    AppInput,
  },
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <h1>Анкета для Vue</h1>
    <AppInput
      type="text"
      placeholder="Введите имя"
      :errName="errors.name"
      nameInp="Имя"
      v-model="nam"
    ></AppInput>
    <AppInput
      type="number"
      placeholder="Введите возраст"
      :errName="errors.name"
      nameInp="Возраст"
      v-model="age"
    />
    <!-- <div class="formgr">
      <label for="age"><strong>Возраст:&nbsp;</strong> </label>
      <input id="age" type="number" v-model.number="age" min="0" />
    </div> -->
    <div class="formgr">
      <label for="city"><strong>Город:&nbsp;</strong> </label>
      <select id="city" v-model="city">
        <option value="orel">Орел</option>
        <option value="vn">Новгород</option>
        <option value="spb">Питер</option>
      </select>
    </div>
    <div class="check">
      <p>Готов к поедке?</p>
      <div class="checkForm">
        <input
          type="radio"
          id="one"
          name="ready"
          value="yes"
          v-model="pereezd"
        />
        <label for="one">Да</label>
      </div>
      <div class="checkForm">
        <input
          type="radio"
          id="two"
          name="ready"
          value="no"
          v-model="pereezd"
        />
        <label for="two">Нет</label>
      </div>
      <hr id="hr" />
      <p>Твои знания?</p>
      <div class="checkForm">
        <input
          type="checkbox"
          id="one"
          v-model="skils"
          name="skil"
          value="vuex"
        />
        <label for="onezn">Знание 1</label>
      </div>
      <div class="checkForm">
        <input
          type="checkbox"
          id="two"
          v-model="skils"
          name="skil"
          value="cli"
        />
        <label for="twozn">Знание 2</label>
      </div>
      <div class="checkForm">
        <input
          type="checkbox"
          id="two"
          v-model="skils"
          name="skil"
          value="router"
        />
        <label for="threezn">Знание 3</label>
      </div>
      <hr id="hr" />
      <div class="checkForm">
        <input type="checkbox" id="agree" v-model="agree" />
        <label for="onezn">С правилами согласен</label>
      </div>
      <button type="submit">Отправить</button>
    </div>
  </form>
</template>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  margin: auto;
  width: 95%;
  height: 600px;
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

select {
  width: 500px;
  border-radius: 5px;
  outline: none;
  border: none;
  padding: 5px;
  color: black;
  font-weight: 500;
}

.check {
  display: flex;
  width: 250px;
  flex-direction: column;
  align-items: flex-start;
}
.checkForm {
  display: flex;
  margin-bottom: 10px;
  text-align: center;
}
.checkForm input {
  width: 20px;
}
.checkForm label {
  width: auto;
}
#hr {
  width: 100%;
}
button {
  padding: 10px;
  width: 130px;
  background-color: rgb(12, 185, 12);
  border: none;
  border-radius: 10px;
  transition: all 0.3s ease;
  color: white;
}
button:hover {
  background-color: green;
}
</style>
