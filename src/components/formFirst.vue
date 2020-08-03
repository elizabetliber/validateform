<template>
    <div>
        <div class="container">
            <form @submit.prevent="registerUser" novalidate>
                <div class="row">
                    <h3>Личные данные:</h3>
                </div>
<pre>
    {{$v.formReg.lastName}}
</pre>
                <div class="row">
                    <div class="col-25">
                        <label for="lastName">Фамилия<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <input @blur="$v.formReg.lastName.$touch()"
                               :style= "{'border: color': $v.formReg.lastName.$error}"
                               type="text"
                               v-model='formReg.lastName'
                               id="lastName"
                               placeholder="Введите фамилию">
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label for="name">Имя<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <input type="text" v-model="formReg.name" id="name" placeholder="Введите имя">
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label for="id">Отчество</label>
                    </div>
                    <div class="col-75">
                        <input type="text" v-model="formReg.id" id="id" placeholder="Введите отчество"/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label for="dateOfBirth">Дата рождения<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <input type="text" v-model="formReg.dateOfBirth" id="dateOfBirth" placeholder="дд.мм.гггг"/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label for="sxx">Пол</label>
                    </div>
                    <div class="col-75">
                        <select id="sxx" v-model="selected">
                            <option disabled value="">Выберите один из вариантов</option>
                            <option  >Мужской</option>
                            <option>Женский</option>
                        </select>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Группа клиентов<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <select v-model="users" multiple>
                            <option disabled value="">Выберите несколько вариантов</option>
                            <option>Паспорт</option>
                            <option>Свидетельство о рождении</option>
                            <option>Водительское удостоверение</option>

                        </select><span>Выбрано: {{users}}</span>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Лечащий врач</label>
                    </div>
                    <div class="col-75">
                        <select v-model="selected">
                            <option disabled value="">Выберите один из вариантов</option>
                            <option>Иванов</option>
                            <option>Захаров</option>
                            <option>Чернышева</option>
                        </select>
                    </div>
                </div>

                <div class="row">
                    <input type="checkbox" checked="checked" v-model="checked" id="checkbox"> Не отправлять СМС
                    <label for="checkbox">{{ checked }}</label>
                </div>

                <div class="row">
                    <h3>Адрес:</h3>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Индекс</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Индекс">
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Страна</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Страна">
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Область</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Область"/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Город<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <input type="text" v-model="message" placeholder="Город"/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Улица</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Улица"/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Дом</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Дом"/>
                    </div>
                </div>
                <div class="row">
                    <h3>Паспорт:</h3>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Тип документа<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <select v-model="selected">
                            <option disabled value="">Выберите один из вариантов</option>
                            <option>Паспорт</option>
                            <option>Свидетельство о рождении</option>
                            <option>Водительское удостоверение</option>
                        </select>
                    </div>

                </div>
                <div class="row">
                    <div class="col-25">
                        <label>Серия</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder=""/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Номер</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder=""/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Кем выдан</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder=""/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Дата выдачи<sup style="color:red;">*</sup></label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder=""/>
                    </div>
                </div>
                <div class="row">
                    <h4><em style="color:red;">*</em> Поле обязательное для заполнения.</h4>
                </div>

                <div class="row">
                    <input type="submit" value="Подтвердить"/>
                </div>

            </form>

        </div>
    </div>
</template>

<script>
  import {required} from 'vuelidate/lib/validators'
  export default {
    data() {
      return {
       color: "1px solid red",
    formReg: {
          lastName: '',
          name: '',
          id: '',
          dateOfBirth: ''

        }
      }
    },
    methods: {
      registerUser: function () {
        console.log("Register true")
        console.log(this.formReg.name)
      }
    },
    validations: {
      formReg: {
        lastName: {
          required
        }
  }
  }
  }
</script>

<style scoped>
    input[type=text], select, textarea {
        width: 100%;
        padding: 12px;
        border: 1px solid lightsteelblue;
        border-radius: 4px;
        box-sizing: border-box;
        resize: vertical;
    }

    /* Style the label to display next to the inputs */
    label {
        padding: 12px 12px 12px 0;
        display: inline-block;
    }

    /* Style the submit button */
    input[type=submit] {
        background-color: #4CAF50;
        color: white;
        padding: 12px 20px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        float: right;
    }

    /* Style the container */
    .container {

        border-radius: 5px;
        background-color: #f2f2f2;
        padding: 20px;
    }

    /* Floating column for labels: 25% width */
    .col-25 {
        float: left;
        width: 25%;
        margin-top: 6px;
    }

    /* Floating column for inputs: 75% width */
    .col-75 {
        text-align: right;
        float: left;
        width: 75%;
        margin-top: 6px;
    }

    /* Clear floats after the columns */
    .row:after {
        content: "";
        display: table;
        clear: both;
    }

    /* Responsive layout - when the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other */
    @media screen and (max-width: 600px) {
        .col-25, .col-75, input[type=submit] {
            width: 100%;
            margin-top: 0;
        }
    }

    .row {
        clear: both;
        text-align: right;
    }
</style>