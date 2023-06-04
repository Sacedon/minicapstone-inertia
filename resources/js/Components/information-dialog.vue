<script setup>
defineProps({
    title: '',
    message: ''
})
defineEmits(['dismiss'])
</script>

<template>
    <!-- Overlay -->
    <div class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-75">
      <!-- Dialog -->
      <div class="bg-white rounded-lg shadow-lg max-w-sm">
        <div class="p-4">
          <h1 class="text-lg font-semibold">Information Message</h1>
          <hr class="my-2">
          <div class="flex items-center space-x-4">
            <span class="text-3xl text-blue-600">
              <i class="fas fa-info-circle"></i>
            </span>
            <p class="text-base">{{ message }}</p>
          </div>
          <hr class="my-2">
          <button class="float-right mt-2 px-4 py-2 text-white bg-blue-500 rounded-md hover:bg-blue-600 mb-3" @click="$emit('dismiss')">Close</button>
        </div>
      </div>
    </div>
  </template>
