<script setup>
import header_component from './components/header.vue';
import content_component from './components/content.vue';
import modal_component from './components/modals.vue'
</script>

<template>
  <div class="wrapper">
    <header_component></header_component>

    <div class="content_wrapper">
        <div class="container_contant">
          <content_component>

          </content_component>
        </div>
    </div>
  </div>
  <modal_component></modal_component>




  
</template>

<style scoped>

</style>
