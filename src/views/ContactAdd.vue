<template>
    <div v-if="contact" class="page">
      <h4>Hiệu chỉnh Liên hệ</h4>
      <ContactForm
        :contact="contact"
        @submit:contact="createContact"
        
      />
      <p>{{ message }}</p>
    </div>
  </template>
  <script>
  import ContactForm from "@/components/ContactForm.vue";
  import ContactService from "@/services/contact.service";
  export default {
    components: {
      ContactForm,
    },
    props: {
      id: { type: String, required: true },
    },
    data() {
      return {
        contact: null,
        message: "",
      };
    },
    methods: {
   
      async createContact(data) {
        try {
          await ContactService.created(data);
          this.message = " thành công.";
        } catch (error) {
          console.log(error);
        }
      },
      
    },
    created() {
      this.contact={};
      this.message = "";
    },
  };
  </script>