<!-- MyModal.vue -->
<template>
    <modal name="my-modal">
      <!-- Your modal content goes here -->
      <div>
        <h2>Hello, I'm a Modal!</h2>
        <button @click="closeModal">Close</button>
      </div>
    </modal>
  </template>
  
  <script>
  export default {
    methods: {
      closeModal() {
        this.$modal.hide('my-modal');
      }
    }
  };
  </script>
  