<script setup lang="ts">
import { ClipboardList, Home, Settings, Users } from 'lucide-vue-next'

const props = defineProps<{
  isSideBarOpen?: boolean
}>()

const emits = defineEmits(['handleSidebar'])

const handleSidebar = () => {
  emits('handleSidebar')
}
</script>

<template>
  <aside id="logo-sidebar"
    class="fixed left-0 z-40 w-64 h-screen pt-20 transition-transform -translate-x-full bg-white border-r border-gray-200 sm:translate-x-0 dark:bg-gray-800 dark:border-gray-700"
    aria-label="Sidebar"
    :class="{ 'translate-x-0': isSideBarOpen, 'left-0': !isSideBarOpen, 'right-0': isSideBarOpen }">
    <div class="h-full px-3 pb-4 overflow-y-auto bg-white dark:bg-gray-800" @click="handleSidebar">
      <ul class="space-y-2 font-medium">
        <li>
          <NuxtLink to="/"
            class="flex items-center p-4 text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700 group">
            <Home :absolute-stroke-width="true"
              class="flex-shrink-0 w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
            <span class="ms-3">Главная</span>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/accounts"
            class="flex items-center p-4 text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700 group">
            <ClipboardList :absolute-stroke-width="true"
              class="flex-shrink-0 w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
            <span class="flex-1 ms-3 whitespace-nowrap">Аккаунты</span>

            <!--            badge on nav menu-->
            <!--            <span class="inline-flex items-center justify-center px-2 ms-3 text-sm font-medium text-gray-800 bg-gray-100 rounded-full dark:bg-gray-700 dark:text-gray-300">Pro</span>-->
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/workers"
            class="flex items-center p-4 text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700 group">
            <Users :absolute-stroke-width="true"
              class="flex-shrink-0 w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
            <span class="flex-1 ms-3 whitespace-nowrap">Воркеры</span>
            <span
              class="inline-flex items-center justify-center w-3 h-3 p-3 ms-3 text-sm font-medium text-blue-800 bg-blue-100 rounded-full dark:bg-blue-900 dark:text-blue-300">3</span>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/settings"
            class="flex items-center p-4 text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700 group">
            <Settings :absolute-stroke-width="true"
              class="flex-shrink-0 w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
            <span class="flex-1 ms-3 whitespace-nowrap">Настройки</span>
          </NuxtLink>
        </li>
      </ul>
    </div>
  </aside>
</template>

<style scoped></style>
