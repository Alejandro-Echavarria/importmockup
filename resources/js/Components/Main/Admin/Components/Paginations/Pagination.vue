<script setup>
import { router } from "@inertiajs/vue3";
import { onBeforeMount, watch } from "vue";

const props = defineProps({
    pagination: {
        type: Object,
        required: true,
    },
});

onBeforeMount(() => {
    if (props.pagination.last_page < props.pagination.current_page) {
        const url = props.pagination.last_page_url;

        router.visit(url);
    }
});

watch(
    () => props.pagination?.data?.length,
    (newLength, oldLength) => {
        // Verificar si la longitud es cero y realizar la redirección
        if (newLength === 0) {
            const prevPageUrl = props.pagination.prev_page_url;

            if (prevPageUrl) {
                router.visit(prevPageUrl);
            }
        }
    }
);

const changePage = (url) => {
    const page = url.split("?page=")[1];
    router.visit(router.page.url, {
        preserveScroll: false,
        preserveState: true,
        data: {
            page: page,
        },
    });
};
</script>

<template>
    <div
        class="flex flex-col md:flex-row items-start md:items-center justify-between space-y-3 md:space-y-0 p-4 border-t"
    >
        <div class="w-full sm:hidden">
            <nav aria-label="Page navigation example">
                <ul class="inline-flex -space-x-px text-sm">
                    <li>
                        <a
                            href="#"
                            class="flex items-center justify-center px-3 h-8 ml-0 leading-tight text-gray-500 bg-white border border-gray-300 rounded-l-lg hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white"
                            >Previous</a
                        >
                    </li>
                    <li>
                        <a
                            href="#"
                            class="flex items-center justify-center px-3 h-8 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white"
                            >1</a
                        >
                    </li>
                    <li>
                        <a
                            href="#"
                            class="flex items-center justify-center px-3 h-8 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white"
                            >2</a
                        >
                    </li>
                    <li>
                        <a
                            href="#"
                            aria-current="page"
                            class="flex items-center justify-center px-3 h-8 text-blue-600 border border-gray-300 bg-blue-50 hover:bg-blue-100 hover:text-blue-700 dark:border-gray-700 dark:bg-gray-700 dark:text-white"
                            >3</a
                        >
                    </li>
                    <li>
                        <a
                            href="#"
                            class="flex items-center justify-center px-3 h-8 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white"
                            >4</a
                        >
                    </li>
                    <li>
                        <a
                            href="#"
                            class="flex items-center justify-center px-3 h-8 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white"
                            >5</a
                        >
                    </li>
                    <li>
                        <a
                            href="#"
                            class="flex items-center justify-center px-3 h-8 leading-tight text-gray-500 bg-white border border-gray-300 rounded-r-lg hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white"
                            >Next</a
                        >
                    </li>
                </ul>
            </nav>
        </div>
        <div
            class="hidden sm:flex sm:flex-1 sm:items-center sm:justify-between"
        >
            <div>
                <p class="text-sm text-gray-700">
                    Showing
                    <span class="font-medium">{{ pagination.from }}</span>
                    to
                    <span class="font-medium">{{ pagination.to }}</span>
                    of
                    <span class="font-medium">{{ pagination.total }}</span>
                    results
                </p>
            </div>
            <div v-if="pagination.links.length > 3">
                <nav
                    class="isolate inline-flex -space-x-px rounded-md"
                    aria-label="Pagination"
                >
                    <template v-for="(link, index) in pagination.links">
                        <div
                            v-if="link.url == null"
                            :key="'botons-' + index"
                            class="relative inline-flex items-center px-4 py-2 text-sm font-semibold text-gray-400 focus:z-20 cursor-not-allowed"
                            v-html="link.label"
                        ></div>

                        <a
                            v-else
                            :key="'links-' + index"
                            @click="changePage(link.url)"
                            class="relative inline-flex items-center px-4 py-2 text-sm font-semibold text-gray-900 focus:z-20 cursor-pointer"
                            :class="
                                link.active
                                    ? 'z-10 border-b-2 border-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500 focus:outline-none focus:border-indigo-500 transition duration-150 ease-in-out'
                                    : ''
                            "
                            v-html="link.label"
                        >
                        </a>
                    </template>
                </nav>
            </div>
        </div>
    </div>
</template>
