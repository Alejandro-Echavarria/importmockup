<script setup>
import { Head } from "@inertiajs/vue3";
import MainLayout from "@/Components/Main/Admin/Layout/MainLayout.vue";
import MainTitle from "@/Components/Main/Admin/Components/Titles/MainTitle.vue";
import Search from "@/Components/Main/Admin/Components/Searchs/Search.vue";
import MainTable from "@/Components/Main/Admin/Components/Tables/MainTable.vue";
import TableButton from "@/Components/Main/Admin/Components/Buttons/TableButton.vue";

defineOptions({
    layout: MainLayout,
});
</script>

<template>
    <div>
        <Head title="Jobs" />

        <MainTitle> Usuarios </MainTitle>

        <MainTable>
            <template #search>
                <Search :filter="h" :url="h" />
            </template>

            <template #createButton>
                <SaveUserSocialMedia
                    ref="callOpenModal"
                    :socialMedias="h"
                    :filter="h"
                    :page="h"
                />
            </template>

            <template #thead>
                <th scope="col" class="px-4 py-3">Name</th>
                <th scope="col" class="px-4 py-3">Email</th>
                <th scope="col" class="px-4 py-3">Creado</th>
                <th scope="col" class="px-4 py-3">Actualizado</th>
            </template>

            <template #tbody>
                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>


                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
                        <TableButton>
                            <font-awesome-icon
                                @click="openModal()"
                                class="w-4 h-4 text-red-500"
                                :icon="['far', 'trash-alt']"
                            />
                        </TableButton>
                    </td>
                </tr>

                <tr
                    class="dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600 transition ease-linear duration-300"
                    :key="h + 'tb'"
                >
                    <td class="px-4 py-3">Manuel Echavarria</td>
                    <td class="px-4 py-3">mechavarria@gmail.com</td>
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
