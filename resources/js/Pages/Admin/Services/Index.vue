<script setup>
import { Head } from '@inertiajs/vue3';
import { ref } from 'vue';
import MainLayout from '@/Components/Main/Admin/Layout/MainLayout.vue';
import MainTitle from '@/Components/Main/Admin/Components/Titles/MainTitle.vue';
import MainTable from '@/Components/Main/Admin/Components/Tables/MainTable.vue';
import TableButton from '@/Components/Main/Admin/Components/Buttons/TableButton.vue';
import Search from '@/Components/Main/Admin/Components/Searchs/Search.vue';
import SaveService from '@/Pages/Admin/Services/Partials/SaveService.vue';
import DeleteService from '@/Pages/Admin/Services/Partials/DeleteService.vue';

defineOptions({
    layout: MainLayout
});

const props = defineProps({
    services: Object,
    filter: String,
    page: String
});

const thead = ['title', 'icon', 'description', 'color', 'created', 'updated'];
const url = 'admin.services.index';
const callOpenModal = ref(null);

const openModal = (op, id, title, icon, description, color) => {
    callOpenModal.value.openModal(op, id, title, icon, description, color);
};
</script>

<template>
    <Head title="Services" />

    <div>
        <MainTitle>
            Roles
        </MainTitle>

        <MainTable :pagination="services">
            <template #search>
                <Search :filter="filter" :url="url" />
            </template>

            <template #createButton>
                <SaveService ref="callOpenModal" :data="services" :filter="filter" :page="page" />
            </template>

            <template #thead>
                <th scope="col" class="px-4 py-3">
                    Nombre
                </th>
                <th scope="col" class="px-4 py-3">
                    Creado
                </th><th scope="col" class="px-4 py-3">
                    Actualizdo
                </th>
            </template>

            <template #tbody>
                <tr class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'">
                    <td class="px-4 py-3">Admin</td>
                    <td class="px-4 py-3">01/01/2020</td>
                    <td class="px-4 py-3">01/01/2020</td>
                    <td class="px-4 py-3 flex items-center justify-end">
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-indigo-500"
                                :icon="['far', 'pen-to-square']"
                            />
                        </TableButton>
                        <TableButton title="Permisos">
                            <svg class="flex-shrink-0 w-4 h-4 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 20">
                  <path d="M16 14V2a2 2 0 0 0-2-2H2a2 2 0 0 0-2 2v15a3 3 0 0 0 3 3h12a1 1 0 0 0 0-2h-1v-2a2 2 0 0 0 2-2ZM4 2h2v12H4V2Zm8 16H3a1 1 0 0 1 0-2h9v2Z"/>
               </svg>
                        </TableButton>
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'">
                    <td class="px-4 py-3">User</td>
                    <td class="px-4 py-3">01/01/2020</td>
                    <td class="px-4 py-3">01/01/2020</td>
                    <td class="px-4 py-3 flex items-center justify-end">
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-indigo-500"
                                :icon="['far', 'pen-to-square']"
                            />
                        </TableButton>
                        <TableButton title="Permisos">
                            <svg class="flex-shrink-0 w-4 h-4 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 20">
                            <path d="M16 14V2a2 2 0 0 0-2-2H2a2 2 0 0 0-2 2v15a3 3 0 0 0 3 3h12a1 1 0 0 0 0-2h-1v-2a2 2 0 0 0 2-2ZM4 2h2v12H4V2Zm8 16H3a1 1 0 0 1 0-2h9v2Z"/>
                        </svg>
                        </TableButton>
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>
            </template>
        </MainTable>
    </div>
</template>