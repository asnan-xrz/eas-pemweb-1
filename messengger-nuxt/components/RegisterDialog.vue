<!-- RegisterDialog.vue -->

<template>
    <div class="register-dialog">
      <form @submit="onSubmit">
        <label for="username">Username:</label>
        <input v-model="username" type="text" required />
  
        <button type="submit">Register</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RegisterDialog',
    data: () => ({
      username: ''
    }),
    methods: {
      onSubmit(event) {
        event.preventDefault();
        // Emit an event to the parent component with the entered username
        this.$emit('submit', event, this.username);
        // You may perform additional registration/authentication logic here
      }
    }
  }
  </script>
  
  <style scoped>
  .register-dialog {
    max-width: 300px;
    margin: auto;
  }
  
  form {
    display: flex;
    flex-direction: column;
  }
  
  label {
    margin-bottom: 0.5rem;
  }
  
  input {
    padding: 0.5rem;
    margin-bottom: 1rem;
  }
  
  button {
    padding: 0.5rem;
    background-color: #2a60ff;
    color: white;
    border: none;
    cursor: pointer;
  }
  </style>
  