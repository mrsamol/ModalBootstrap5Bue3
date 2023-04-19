<script setup lang="ts">
import { defineProps } from 'vue';
defineProps({
  show: {
    type: Boolean,
    default: false,
  },
  title: {
    type: String,
    default: "Hello World",
  },
});

</script>
<template>
<div class="modal fade" :class="{ show: show, 'd-block': show }" ref="modal">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">{{ title }}</h5>
          <slot name="header" /> 
        </div>
        <div class="modal-body">
          <slot name="body" />
        </div>
        <div class="modal-footer">
          <slot name="footer" />           
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
