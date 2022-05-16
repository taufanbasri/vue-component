<template>
  <form @submit.prevent="submitData">
      <div>
          <label for="name">Name</label>
          <input v-model="contact.enteredName" type="text">
      </div>
      <div>
          <label for="phone">Phone</label>
          <input v-model="contact.enteredPhone" type="tel">
      </div>
      <div>
          <label for="email">Email</label>
          <input v-model="contact.enteredEmail" type="email">
      </div>
      <div>
          <button>Add Contact</button>
      </div>
  </form>
</template>

<script>
export default {
    emits: ['add-contact'],
    data() {
        return {
            contact: {
                enteredName: '',
                enteredEmail: '',
                enteredPhone: ''
            }
        }
    },
    methods: {
        submitData() {
            this.$emit('add-contact', this.contact)
        }
    },
}
</script>