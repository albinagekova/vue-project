<template>
  <div class="overlay" v-if="showModal">
    <div class="container">
      <div class="modalContainer">
        <div class="modalTitle">
          <div />
          <h3>{{title}}</h3>
          <div>
            <a class="close" @click="$emit('closeModal')" />
          </div>
        </div>
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup>
  import { defineProps } from 'vue';
    defineProps({
      showModal: {
        type: Boolean,
        required: true,
      },
      title: {
        type: String,
        required: true,
      },
    })
</script>

<style scoped>
  .overlay {
    position: fixed;
    width: 100%;
    height: 100vh;
    background: rgba(128, 128, 128, 0.6);
    top: 0px;
    left: 0px;
  }
  .modalContainer {
    min-width: 800px;
    background: #707070;
    border-radius: 10px;
  }
  .container {
    font-weight: 400;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }
  .modalTitle {
    color: white;
    font-weight: normal;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 1em;
  }
  .modalTitle div {
    position: relative;
  }
  .close {
    position: absolute;
    right: 10px;
    top: -10px;
    width: 32px;
    height: 32px;
    opacity: 0.5;
    cursor: pointer;
  }
  .close:hover {
    opacity: 1;
  }
  .close:before, .close:after {
    position: absolute;
    left: 15px;
    content: ' ';
    height: 33px;
    width: 2px;
    background-color: white;
  }
  .close:before {
    transform: rotate(45deg);
  }
  .close:after {
    transform: rotate(-45deg);
  }
   h1, h2, h3, h4, h5, h6 {
    font-weight: 300;
  }

</style>
