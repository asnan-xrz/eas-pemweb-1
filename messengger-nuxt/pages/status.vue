<!-- /pages/status.vue -->

<template>
    <div>
      <h1>Cek Status Pendaftaran</h1>
      <form @submit.prevent="checkStatus">
        <label for="email">Email:</label>
        <input v-model="email" type="email" id="email" required />
  
        <button type="submit">Check Status</button>
      </form>
  
      <!-- Display status here -->
      <div v-if="status !== null">
        <p>Status Pendaftaran: {{ status }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        email: '',
        status: null,
      };
    },
    methods: {
      checkStatus() {
        // Implement logic to fetch and display status based on the email
        console.log('Checking status for email:', this.email);
  
        // Example: Assume you have an API endpoint to fetch status
        // Replace the following code with actual API call
        this.status = 'Waiting'; // Set status based on API response
      },
    },
  };
  </script>
  