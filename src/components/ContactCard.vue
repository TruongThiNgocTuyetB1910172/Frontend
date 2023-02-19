<script>
export default {
  props: {
    contact: {
      type: Object,
      required: true,
    },
  },
};
</script>
<template>
  <div class="p-1">
    <strong> Ten: </strong>
    {{ contact.name }}
  </div>
  <div class="p-1">
    <strong> Email: </strong>
    {{ contact.email }}
  </div>
  <div class="p-1">
    <strong> Dia chi: </strong>
    {{ contact.address }}
  </div>
  <div class="p-1">
    <strong> Phone: </strong>
    {{ contact.phone }}
  </div>
  <div class="p-1">
    <strong>Liên hệ yêu thích:&nbsp;</strong>
    <i v-if="contact.favorite" class="fas fa-check"></i>
    <i v-else class="fas fa-times"></i>
  </div>
</template>
