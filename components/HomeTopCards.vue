<script lang="ts" setup>
import { Icon } from '@iconify/vue'
</script>

<template>
  <div class="grid grid-cols-2 gap-2 mb-4 lg:grid-cols-3 xl:grid-cols-4 xl:gap-4">
    <div class="flex items-center justify-center h-full rounded">
      <Card class="w-full">
        <CardHeader class="flex flex-row items-center justify-between space-y-0 w-full p-4 pb-2">
          <CardTitle class="text-sm font-medium"> Свободных аккаунтов </CardTitle>
          <Icon icon="mdi:accounts-switch" class="h-6 w-6 text-muted-foreground" />
        </CardHeader>
        <CardContent class="p-4 pt-2">
          <div class="text-2xl font-bold">2</div>
          <p class="text-xs text-muted-foreground">активность сегодня: 3</p>
        </CardContent>
      </Card>
    </div>
    <div class="flex items-center justify-center h-full rounded">
      <Card class="w-full">
        <CardHeader class="flex flex-row items-center justify-between space-y-0 w-full p-4 pb-2">
          <CardTitle class="text-sm font-medium"> Аккаунтов в работе </CardTitle>
          <Icon icon="ic:baseline-paypal" class='h-6 w-6 text-muted-foreground' />
        </CardHeader>
        <CardContent class="p-4 pt-2">
          <div class="text-2xl font-bold">4</div>
          <p class="text-xs text-muted-foreground">активность сегодня: 3</p>
        </CardContent>
      </Card>
    </div>
    <div class="flex items-center justify-center h-full rounded">
      <Card class="w-full">
        <CardHeader class="flex flex-row items-center justify-between space-y-0 p-4 pb-2 w-full">
          <CardTitle class="text-sm font-medium"> Всего воркеров </CardTitle>
          <Icon icon="gravity-ui:person-worker" class="h-6 w-6 text-muted-foreground" />
        </CardHeader>
        <CardContent class="p-4 pt-2">
          <div class="text-2xl font-bold">24</div>
          <p class="text-xs text-muted-foreground">активность сегодня: 3</p>
        </CardContent>
      </Card>
    </div>
    <div class="flex items-center justify-center h-full rounded">
      <Card class="w-full">
        <CardHeader class="flex flex-row items-center justify-between space-y-0 p-4 pb-2 w-full">
          <CardTitle class="text-sm font-medium"> Всего заведено </CardTitle>
          <Icon icon="f7:money-euro-circle-fill" class="h-6 w-6 text-muted-foreground" />
        </CardHeader>
        <CardContent class="p-4 pt-2">
          <div class="text-2xl font-bold">1 232 €</div>
          <p class="text-xs text-muted-foreground">сегодня: 252 €</p>
        </CardContent>
      </Card>
    </div>
  </div>
</template>

<style></style>