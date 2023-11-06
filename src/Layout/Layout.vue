<script setup>
import Header from "./Header/Header.vue"
import Sidebar from "./Sidebar/Sidebar.vue"
</script>

<template>
  <div class="grid-container">
    <Sidebar />
    <div class="content-container">
      <Header />
      <main class="main">
        <slot></slot>
      </main>
    </div>
  </div>
</template>

<style>
.grid-container {
  display: grid;
  grid-template-areas:
    "sidebar content";
  grid-template-rows: 1fr;
  grid-template-columns: 260px 1fr;
  height: 100vh;
  overflow: hidden;
}

.content-container {
  grid-area: content;
  display: flex;
  flex-direction: column;
  overflow: auto;
	padding: 20px 20px 0 20px;
}

.main {
  background-color: #f0f0f0;
  overflow-y: auto;
  padding: 20px;
  box-sizing: border-box;
  position: relative;
  flex: 1;
}

.Sidebar {
  grid-area: sidebar;
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  width: 260px;
  z-index: 1000;
  background-color: #ddd;
  overflow-y: auto;
  padding: 20px;
}

.Header {
  position: fixed;
  top: 0;
  left: 260px;
  width: calc(100% - 260px);
  height: 80px;
  z-index: 1000;
  background-color: #333;
  color: #fff;
  padding: 20px;
}
</style>