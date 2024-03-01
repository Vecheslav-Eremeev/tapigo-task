<template>
  <div class="flex min-h-full flex-col justify-center px-6 py-12 lg:px-8">
    <div class="sm:mx-auto sm:w-full sm:max-w-sm">
      <h2
        class="mt-10 text-center text-2xl font-bold leading-9 tracking-tight text-gray-900"
      >
        Вход в ваш аккунт
      </h2>
    </div>

    <div class="mt-10 sm:mx-auto sm:w-full sm:max-w-sm">
      <form class="space-y-6" @submit.prevent="login">
        <div>
          <label
            for="fio"
            class="block text-sm font-medium leading-6 text-gray-900"
            >Фамилия и имя</label
          >
          <div class="mt-2">
            <input
              id="fio"
              name="fio"
              type="text"
              required
              v-model="fullName"
              @input="validateFullName"
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6 px-3"
            />
            <p v-if="fullNameError" class="text-red-600 text-sm">
              {{ fullNameError }}
            </p>
          </div>
        </div>

        <div>
          <label
            for="phone"
            class="block text-sm font-medium leading-6 text-gray-900"
            >Номер телефона:</label
          >
          <div class="mt-2">
            <input
              id="phone"
              name="phone"
              type="text"
              required
              v-model="phoneNumber"
              @input="validatePhoneNumber"
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6 px-3"
            />
            <p v-if="phoneNumberError" class="text-red-600 text-sm">
              {{ phoneNumberError }}
            </p>
          </div>
        </div>

        <div>
          <label
            for="email"
            class="block text-sm font-medium leading-6 text-gray-900"
            >Почта:</label
          >
          <div class="mt-2">
            <input
              id="email"
              name="email"
              type="email"
              required
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6 px-3"
            />
          </div>
        </div>

        <div>
          <div class="flex items-center justify-between">
            <label
              for="password"
              class="block text-sm font-medium leading-6 text-gray-900"
              >Пароль:</label
            >
          </div>
          <div class="mt-2">
            <input
              id="password"
              name="password"
              type="password"
              required
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6 px-3"
            />
          </div>
        </div>

        <div>
          <button
            type="submit"
            class="flex w-full justify-center rounded-md bg-indigo-600 px-3 py-1.5 text-sm font-semibold leading-6 text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          >
            Отправить
          </button>
        </div>
      </form>
    </div>
  </div>
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
    login() {
      if (!this.fullNameError && !this.phoneNumberError) {
        console.log(
          "Отправка данных:",
          this.fullName,
          this.phoneNumber,
          this.email,
          this.password
        );
        this.$store.dispatch("login");
        this.$router.push("/movie");
      } else {
        console.log("Форма содержит ошибки");
      }
    },
  },
};
</script>
