<script setup>
import { Head, useForm, Link } from '@inertiajs/vue3';
import { onMounted, onUnmounted } from 'vue';
import MainLayout from '@/Components/Main/Admin/Layout/MainLayout.vue';
import MainTitle from '@/Components/Main/Admin/Components/Titles/MainTitle.vue';
import SimpleForm from '@/Components/Main/Admin/Components/Forms/SimpleForm.vue';
import TextInput from '@/Components/TextInput.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import SaveAlert from '@/Helpers/Alerts/SaveAlert';
import Datepicker from 'flowbite-datepicker/Datepicker';
import Ckeditor from '@/Components/Main/Admin/Components/Forms/Inputs/ckeditor/Ckeditor.vue';

defineOptions({
    layout: MainLayout
});

const props = defineProps({
    auth: Object
});

onMounted(() => {
    const datedatepickerId2pickerEl = document.querySelector('#datepickerId');

    new Datepicker(datedatepickerId2pickerEl, {
        autohide: true,
        format: 'dd/mm/yyyy',
        todayHighlight: true
    });
});

onUnmounted(() => {
    const datedatepickerId2pickerEl = document.querySelector('.datepicker');

    datedatepickerId2pickerEl.remove();
});

const form = useForm({
    position: props.auth.user.position,
    bio: props.auth.user.bio,
    address: props.auth.user.address,
    phone: props.auth.user.phone,
    birthday: props.auth.user.birthday
});

const save = () => {
    const datedatepickerId2pickerEl = document.querySelector('#datepickerId');

    form.transform((data) => ({
        ...data,
        birthday: datedatepickerId2pickerEl.value
    })).put(route('admin.aboutme.update', props.auth.user.id), {
        preserveScroll: true,
        onSuccess: () => {
            ok('Your ifnormation was updated successfully');
        },
        onError: () => {

        }
    });
};

const ok = (msj, type, timer) => {
    SaveAlert(msj, type, timer);
};
</script>

<template>
    <Head title="About me" />

    <div>
        <MainTitle>
            Configuraciones del sistema
        </MainTitle>

        <main class="h-auto">
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 mb-4">
        <div
          class="border-2 border-dashed border-gray-300 rounded-lg dark:border-gray-600 h-32 md:h-64"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-32 md:h-64"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-32 md:h-64"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-32 md:h-64"
        ></div>
      </div>
      <div
        class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-96 mb-4"
      ></div>
      <div class="grid grid-cols-2 gap-4 mb-4">
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
      </div>
      <div
        class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-96 mb-4"
      ></div>
      <div class="grid grid-cols-2 gap-4">
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
        <div
          class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-48 md:h-72"
        ></div>
      </div>
    </main>
    </div>
</template>
