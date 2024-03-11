<script>
export default {
    data() {
        return {
            city: "",
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
            <h1 class="title_content">погода </h1>
            <h2 class="short_desc_content">bot-Зефир: Привет давай посмотри погду в твоем городе.</h2>
            <h2 class="short_desc_content">bot-Зефир: В каком городе ты бы хотел узнать погоду</h2>
            <h2 class="short_desc_content">bot-Зефир: В каком городе ты бы хотел узнать погоду</h2>

            <h2  class="short_desc_content">You: {{ city }}</h2>

            <div class="input-group mb-3">

                <input type="text" v-model="city" class="form-control" aria-label="Default"
                    aria-describedby="inputGroup-sizing-default">
                    <button v-show="city != ''" type="button" class="btn btn-primary btn-lg">Large button</button>
            </div>

        </div>
    </div>
</template>

<style></style>