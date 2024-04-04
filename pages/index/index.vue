<script lang="ts" setup>
import {ref} from "vue"

const email = ref<string>("")

const isMobile = computed(() => {
    if (process.client) {
        return window.innerWidth < 768
    } else {
        return false
    }
})
</script>

<template>
    <div class="flex justify-between">
        <h2 class="text-2xl text-gray-900 mb-4 font-medium dark:text-white">
            Общая информация
        </h2>
        <Dialog>
            <DialogTrigger as-child>
                <Button>
                    <Icon name="mdi:account-plus" class="h-5 w-5 lg:mr-2"/>
                    <ClientOnly>
                        {{ !isMobile ? "Добавить аккаунт" : "" }}
                    </ClientOnly>
                </Button>
            </DialogTrigger>
            <DialogContent class="w-[calc(100%-32px)] sm:max-w-[425px]">
                <DialogHeader>
                    <DialogTitle>Добавить аккаунт</DialogTitle>
                    <DialogDescription>
                        Для того, чтобы добавить аккаунт, просто введи ниже email
                    </DialogDescription>
                </DialogHeader>
                <div class="grid gap-4 py-4">
                    <div class="flex items-center gap-4">
                        <Label for="name" class="text-left text-md"> Email: </Label>
                        <Input type="email" id="email" v-model="email" placeholder="email@gmail.com" class="text-md"/>
                    </div>
                </div>
                <DialogFooter class="flex flex-row justify-between gap-4">
                    <Button type="submit" class="w-1/2">
                        <Icon name="pepicons-pop:refresh" class="w-4 h-4 mr-2 animate-spin"/>
                        Добавить
                    </Button>
                    <DialogClose as-child>
                        <Button variant="destructive" class="w-1/2">Закрыть</Button>
                    </DialogClose>
                </DialogFooter>
            </DialogContent>
        </Dialog>
    </div>
    <HomeTopCards/>
    <Hometables/>
    <Overview />
</template>

<style></style>
