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
          <div class="flex items-center space-x-4">
            <span class="text-3xl text-red-500">
              <i class="fas fa-exclamation-triangle"></i>
            </span>
            <h1 class="text-lg font-semibold">Warning!</h1>
          </div>
          <hr class="my-2">
          <p class="text-base">{{ message }}</p>
          <hr class="my-4">
          <button class="px-4 py-2 text-white bg-gray-500 rounded-md hover:bg-gray-600 float-right mb-3" @click="$emit('dismiss')">Cancel</button>
        </div>
      </div>
    </div>
  </template>

