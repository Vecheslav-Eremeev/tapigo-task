<template>
  <form @submit.prevent="submitForm">
    <div>
      <label for="fullName">ФИО:</label>
      <input
        type="text"
        id="fullName"
        v-model="fullName"
        @input="validateFullName"
      />
      <p v-if="fullNameError" style="color: red">{{ fullNameError }}</p>
    </div>

    <div>
      <label for="phoneNumber">Номер телефона:</label>
      <input
        type="text"
        id="phoneNumber"
        v-model="phoneNumber"
        @input="validatePhoneNumber"
      />
      <p v-if="phoneNumberError" style="color: red">{{ phoneNumberError }}</p>
    </div>
    
    <div>
      <label for="email">Почта:</label>
      <input type="email" id="email" v-model="email" />
    </div>
    <div>
      <label for="password">Пароль:</label>
      <input type="password" id="password" v-model="password" />
    </div>
    <button type="submit">Отправить</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      fullName: "",
      fullNameError: null,
      phoneNumber: "",
      phoneNumberError: null,
      email: "",
      password: "",
    };
  },
  methods: {
    validateFullName() {
      const nameRegex = /^[а-яА-Я]+\s[а-яА-Я]+$/;
      if (!nameRegex.test(this.fullName)) {
        this.fullNameError =
          "ФИО должно содержать только кириллические символы и состоять из двух слов";
      } else {
        this.fullNameError = null;
      }
    },
    validatePhoneNumber() {
      const phoneRegex = /^\+7\d{10}$/;
      if (!phoneRegex.test(this.phoneNumber)) {
        this.phoneNumberError =
          "Номер телефона должен начинаться с +7 и состоять из 11 цифр";
      } else {
        this.phoneNumberError = null;
      }
    },
    submitForm() {
      if (!this.fullNameError && !this.phoneNumberError) {
        // Отправка данных
        console.log(
          "Отправка данных:",
          this.fullName,
          this.phoneNumber,
          this.email,
          this.password
        );
      } else {
        console.log("Форма содержит ошибки");
      }
    },
  },
};
</script>
