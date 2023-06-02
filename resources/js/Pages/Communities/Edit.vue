<template>
    <Head title="Edit Community" />
  
    <AuthenticatedLayout>
      <template #header>
        <h2 class="font-semibold text-xl text-gray-800 leading-tight">Edit Community</h2>
      </template>
  
      <div class="py-12">
        <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="bg-white rounded-lg shadow-md">
            <div class="p-6">
              <form @submit.prevent="submit">
                <div class="mb-6">
                  <InputLabel for="name" value="Name" />
  
                  <TextInput
                    id="name"
                    type="text"
                    class="mt-1 block w-full"
                    v-model="form.name"
                    required
                    autofocus
                    autocomplete="name"
                  />
  
                  <InputError class="mt-2" :message="form.errors.name" />
                </div>
  
                
                <div class="mb-6">
                  <InputLabel for="description" value="Description" />
  
                  <TextInput
                    id="description"
                    type="text"
                    class="mt-1 block w-full"
                    v-model="form.description"
                    required
                    autofocus
                    autocomplete="description"
                  />
  
                  <InputError class="mt-2" :message="form.errors.description" />
                </div>
  
                <div class="flex justify-end mt-6">
                  <PrimaryButton :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                    Update
                  </PrimaryButton>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </AuthenticatedLayout>
  </template>
  

<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, useForm } from '@inertiajs/vue3';


const props = defineProps({
    community: Object,
})
const form = useForm(props.community);

const submit = () => {
    form.put(route("communities.update", props.community.slug));
};
</script>