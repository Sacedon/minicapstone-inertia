<template>
    <!-- Overlay -->
    <div class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-75">
      <!-- Dialog -->
      <div class="bg-white rounded-lg shadow-lg max-w-sm">
        <div class="p-6">
          <h1 class="text-2xl font-semibold">{{ title }}</h1>
          <hr class="my-4">
          <p class="text-base text-center">{{ message }}</p>
          <div class="mt-6 flex justify-end space-x-4">
            <button class="px-4 py-2 text-white bg-red-500 rounded-md hover:bg-gray-600" @click="$emit('cancel')">Cancel</button>
            <button class="px-4 py-2 text-white bg-green-500 rounded-md hover:bg-blue-600" @click="$emit('confirm')">Confirm</button>
          </div>
        </div>
      </div>
    </div>
  </template>



<script setup>
defineProps({
    title: '',
    message: ''
})
defineEmits(['cancel', 'confirm'])
</script>
