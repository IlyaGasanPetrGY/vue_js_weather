<script>
import axios from 'axios'
export default {
    data() {
        return {
            city: "",
            error: "",
            info: null
            
        }
    },
    computed: {
        cityName(){
            return "<<"+this.city+">>"
        },
        showTemp() {
            return 'Текущаяя температура '+ this.info.main.temp
        },
        showTempLike () {
            return 'Как ощущается температура '+ this.info.main.feels_like
        },
        showTempMin () {
            return 'Минимальная температура '+ this.info.main.temp_min
        },
        showTempMax () {
            return 'макксимальная темепература '+ this.info.main.temp_max
        },


    },
    methods: {
        getWheather() {

            if (this.city.trim().length < 2) {
                this.error = 'введите город'
                return false
            }
            else {
                axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=70bdea441edb6e7ac2781039218a428e`)
                .then(res => (this.info = res.data))
            }
        }
    }
    
}
</script>
<template>
    <div class="container_block">
        <div class="image_content">
            <div class="wrapper_image">
                <img src="./../assets/images/mo.jpg" alt="" class="image_holder">
            </div>
        </div>
        <div class="container_block_content_wrapper">
            <h1 class="title_content">Погода на сегодня </h1>
            <div class="description_block">
                <h2 class="short_desc_content">bot-Зевс: Привет давай посмотри погду в твоем городе.</h2>
                <h2 class="short_desc_content">bot-Зевс: В каком городе ты бы хотел узнать погоду</h2>
                <h2 class="short_desc_content">bot-Зевс: В каком городе ты бы хотел узнать погоду</h2>
            </div>
            
            <h2  class="short_desc_content">You: {{ cityName }}</h2>

            <div class="input-group mb-3">

                <input type="text" v-model="city" class="form-control" aria-label="Default"
                    aria-describedby="inputGroup-sizing-default">
                    <button v-if="city != ''" @click="getWheather()" type="button"  data-toggle="modal" data-target="#exampleModalCenter" class="btn btn-primary btn-lg">Large button</button>
                    <button v-else disabled @click="getWheather()" type="button" class="btn btn-primary btn-lg">Large button</button>
                    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalCenter">
                        Launch demo modal
                      </button>
            </div>
            <p style="color:red"> {{ error }} </p>
            <div v-if="info != null">
                <p >{{ showTemp }}</p>
                <p >{{ showTempLike }}</p>
                <p >{{ showTempMin }}</p>
                <p >{{ showTempMax }}</p>
            </div>
    
            
        </div>
    </div>
    
    
</template>

<style></style>