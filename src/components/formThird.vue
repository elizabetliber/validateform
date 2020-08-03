<template>
  <div>
    <form
        id="app"
        @submit="checkForm"
        method="post"
    >
<!--        novalidate="true"-->


      <div v-if="errors.length">
        <b>Пожалуйста исправьте указанные ошибки:</b>
      <ul>
        <li v-for="error in errors" :key="error" >{{error}}</li>
      </ul>
      </div>

      <p>
        <label for="name">Имя</label>
        <input
            id="name"
            v-model="name"
            type="text"
            name="name"
            :class="{mistake:true}"
        >
      </p>

      <p>
        <label for="lastName">Фамилия</label>
        <input
            id="lastName"
            v-model="lastName"
            type="text"
            name="lastName"
        >
      </p>
      <p>
        <label for="patronymic">Отчество</label>
        <input
            id="patronymic"
            v-model="patronymic"
            type="text"
            name="patronymic"
        >
      </p>
      <p>
        <label for="data">Дата рождения</label>
        <input
            id="data"
            v-model="data"
            type="text"
            name="data"
        >
      </p>
      <p>
        <label for="number">Номер телефона</label>
        <input
            id="number"
            v-model="number"
            type="text"
            name="number"
        >
      <br/>
        <select v-model="selectedUsers" multiple>
          <option v-for="user in users" :key="user">{{user.name}}</option>
<!--          <option>Блюз</option>-->
<!--          <option>Рок</option>-->
<!--          <option>Классика</option>-->
        </select>
        <span id="sel">{{selectedUsers}}</span>
      <p>

        <input
            type="submit"
            value="Отправить"
        >
      </p>

    </form>
  </div>
</template>

<script>


export default {
  data() {
    return {
      errors: [],
      name: null,
      number: null,
      lastName:null,
      data:null,
      patronymic: null,
      users:[
        {name:'Tom'},
        {name:'Bob'},
        {name:'Sam'},
        {name:'Alice'}
      ],
      selectedUsers:[],
    }
  },
  methods: {
    checkForm: function (e) {
      if (this.name && this.age && this.lastName && this.number && this.selectedUsers) return true;
      this.errors = [];
      if (!this.name) this.errors.push("Заполните поле Имя.");
      if (!this.lastName) this.errors.push("Заполните поле Фамилия.")
      if (!this.patronymic) this.errors.push("Заполните поле Отчество.")

      if(this.selectedUsers=="") {
        this.errors.push("Заполните поле select.")
      }else if(this.selectedUsers.length < 2 ){
        this.errors.push("Нужно выбрать несколько вариантов")
      }else{
        let selected = Array.from(this.selectedUsers.options)
            .filter(option => option)
            .map(option => option);
        this.selectedUsers.push(selected)
      }

      if (!this.number) {
        this.errors.push('Укажите номер телефона.');
      } else if (!this.validPhoneNumber(this.number)) {
        this.errors.push('Укажите корректный номер в формате: +7(903)-888-88-88 или 8(999)-99-999-99)');
      }
      if (!this.data) {
        this.errors.push('Укажите дату рождения.');
      } else if (!this.validData(this.data)) {
        this.errors.push('Укажите корректную дату в формате: DD-MM-YYYY или DD.MM.YYYY или DD/MM/YYYY .');
      }
      e.preventDefault();
    },
    validPhoneNumber: function (number) {
      let nu = /^\+?[78][-(]?\d{3}\)?-?\d{3}-?\d{2}-?\d{2}$/;
      return nu.test(number);
    },
    validData: function (data) {
      let hi = /^\d{2}[./-]\d{2}[./-]\d{4}$/;
      return hi.test(data);
    }
  },
}

</script>

<style scoped>

</style>