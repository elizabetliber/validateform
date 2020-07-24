<template>
    <div>
        <div class="container">
            <form action="">
                <div class="row">
                    <div class="col">
                        <label><h3>Личные данные:</h3></label>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Фамилия</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your name..">
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Имя</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your last name..">
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Отчество</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Дата рождения</label>
                    </div>
                    <div class="col-75">
                        <input type="text"  placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label for="sex">Пол</label>
                    </div>
                    <div class="col-75">
                        <select id="sex" name="sex">
                            <option value="man">Мужской</option>
                            <option value="woman">Женский</option>
                        </select>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Группа клиентов</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Лечащий врач</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <input type="checkbox" checked="checked"/> Не отправлять СМС
                </div>

                <div class="row">
                    <div class="col">
                        <label><h3>Адрес:</h3></label>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Индекс</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Страна</label>
                    </div>
                    <div class="col-75">
                        <input type="text" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Область</label>
                    </div>
                    <div class="col-75">
                        <input type="text"  placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Город</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="nao" name="lastname" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Улица</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="nal" name="lastname" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <div class="col-25">
                        <label>Дом</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="na" name="lastname" placeholder="Your last name.."/>
                    </div>
                </div>

                <div class="row">
                    <input type="submit" value="Submit"/>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
  export default {
    name: "lastName"
  }
</script>

<style scoped>
    input[type=text], select, textarea {
        width: 100%;
        padding: 12px;
        border: 1px solid #ccc;
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
h3{
    text-align: center;
}
</style>