<script setup>
import { ref } from "vue";
import ModalHaveFooter from "@/modal/ModalHaveFooter.vue";
// import ModalNoFooter from "@/modal/ModalNoFooter.vue";

let modalVisible = ref(false);

function showModal() {
  modalVisible.value = true;
}
const closeModal = (() => {
  modalVisible.value = false
})
</script>

<template>
  <button @click="showModal">Show Modal</button>
  <ModalHaveFooter title="Create User" :show="modalVisible">
    <template #header>
      <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close" @click="closeModal"></button>
    </template>
    <template #body>
      <p>Modal with Footer</p>
    </template>
    <template #footer>
      <button class="btn btn-primary">Save</button>
      <button type="button" class="btn btn-secondary" data-bs-dismiss="modal" @click="closeModal">
        Close
      </button>
    </template>
  </ModalHaveFooter>
  <!-- <ModalNoFooter title="Create User" :show="modalVisible">
    <template #header>
      <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close" @click="closeModal"></button>
    </template>
    <template #body>
      <p>Modal with Footer</p>
    </template>
    <template #footer>
      <button class="btn btn-primary">Save</button>
      <button type="button" class="btn btn-secondary" data-bs-dismiss="modal" @click="closeModal">
        Close
      </button>
    </template>
  </ModalNoFooter> -->
</template>