<script setup>
import { RouterLink, RouterView } from 'vue-router'
import chatGalery from '../src/components/chatGalery.vue'
</script>

<template>
  <div class="container">
    <div class="app-header"></div>
    <div class="app-chatBox"></div>
    <div class="app-sidebar-left"></div>
    <div class="app-sidebar-right"></div>
    <chatGalery class="app-chatGalery">

    </chatGalery>
  </div>
</template>

<style>
a {
  color: #fff;
  text-decoration: none;
}

body {
  background-color: black;
  color: #fff;
  overflow-y: hidden;
}

* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}

.container {
  margin: 0px;
  padding: 0px;
  height: 100vh;
  width: 100vw;
  display: grid; 
  grid-template-columns: 0.6fr 1.8fr 0.6fr; 
  grid-template-rows: 0.3fr 2.1fr 0.6fr; 
  gap: 0px 0px; 
  grid-template-areas: 
    "app-header app-header app-header"
    "app-sidebar-left app-chatBox app-sidebar-right"
    "app-chatGalery app-chatGalery app-chatGalery"; 
}
.app-chatGalery {
  grid-area: app-chatGalery;
  border-top: 1px solid #fff;
}
.app-chatBox {
  grid-area: app-chatBox;
}
.app-header {
  grid-area: app-header;
}
.app-sidebar-left {
  grid-area: app-sidebar-left;
}
.app-sidebar-right {
  grid-area: app-sidebar-right;
}
</style>