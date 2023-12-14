<!-- /pages/Registration.vue -->

<template>
  <div>
    <h1>Form Registrasi</h1>
    <form @submit.prevent="submitForm">
      <label for="name">Nama:</label>
      <input v-model="formData.name" type="text" id="name" required />

      <label for="email">Email:</label>
      <input v-model="formData.email" type="email" id="email" required />

      <label for="asalSekolah">Asal Sekolah:</label>
      <input v-model="formData.asalSekolah" type="text" id="asalSekolah" />

      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: '',
        email: '',
        asalSekolah: '',
      },
    };
  },
  methods: {
    async submitForm() {
      try {
        const response = await this.$axios.post(
          'http://localhost:3100/api/pendaftaran',
          this.formData
        );

        // Assuming the response contains the status or any other information
        console.log('Form submitted successfully:', response.data.docs);

        // You can redirect to another page or show a success message
        // For example, redirect to a thank you page
        this.$router.push('/thank-you');
      } catch (error) {
        console.error('Error submitting form:', error);

        // Handle error, show error message, etc.
        // You can set an error message in the component's data and display it in the template
      }
    },
  },
};
</script>


  