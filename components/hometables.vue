<script lang="ts" setup>
import { Icon } from '@iconify/vue'

const isMobile = computed(() => {
  if (process.client) {
    return window.innerWidth < 768
  } else {
    return false
  }
})

</script>

<template>
  <main class="flex flex-1 flex-col gap-4 md:gap-8">
    <div class="grid gap-4 md:gap-8 lg:grid-cols-2 xl:grid-cols-3">
      <Card class="xl:col-span-2">
        <CardHeader class="flex flex-row">
          <div class="grid gap-2">
            <CardTitle>Аккаунты в работе</CardTitle>
            <CardDescription>
              Список аккаунтов которые в данный момент находятся в работе
            </CardDescription>
          </div>
          <Button as-child size="sm" class="ml-auto gap-3">
            <a href="#" class="uppercase">
                <ClientOnly>
                    {{ !isMobile ? 'Посмотреть все' : '' }}
                </ClientOnly>
              <Icon icon="akar-icons:link-out"
                class="flex-shrink-0 w-5 h-5 text-gray-200 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
            </a>
          </Button>
        </CardHeader>
        <CardContent>
          <Table class="w-full">
            <TableHeader>
              <TableRow>
                <TableHead>Воркер</TableHead>
                <TableHead class="hidden xl:table-cell"> Аккаунт </TableHead>
                <TableHead class="xl:table-cell"> Статус </TableHead>
                <TableHead class="hidden xl:table-cell"> Дата </TableHead>
                <TableHead class="text-right"> Сумма </TableHead>
              </TableRow>
            </TableHeader>
            <TableBody>
              <TableRow>
                <TableCell>
                  <div class="font-medium">@alex_x15</div>
                </TableCell>
                <TableCell class="hidden xl:table-cell"> testaccount@gmail.com </TableCell>
                <TableCell class="xl:table-cell">
                  <Badge class="text-xs" variant="secondary"> busy </Badge>
                </TableCell>
                <TableCell class="hidden md:table-cell lg:hidden xl:table-cell">
                  2023-06-23, 12:23
                </TableCell>
                <TableCell class="text-right"> – </TableCell>
              </TableRow>
              <TableRow>
                <TableCell>
                  <div class="font-medium">@first_name</div>
                </TableCell>
                <TableCell class="hidden xl:table-cell"> account2@gmail.com </TableCell>
                <TableCell class="xl:table-cell">
                  <Badge class="text-xs" variant="default"> done </Badge>
                </TableCell>
                <TableCell class="hidden md:table-cell lg:hidden xl:table-cell">
                  2023-06-23, 12:23
                </TableCell>
                <TableCell class="text-right"> 85 € </TableCell>
              </TableRow>
              <TableRow>
                <TableCell>
                  <div class="font-medium">@plastmas</div>
                </TableCell>
                <TableCell class="hidden xl:table-cell"> oliviabrand@gmail.com </TableCell>
                <TableCell class="xl:table-cell">
                  <Badge class="text-xs" variant="secondary"> busy </Badge>
                </TableCell>
                <TableCell class="hidden md:table-cell lg:hidden xl:table-cell">
                  2023-06-23, 12:23
                </TableCell>
                <TableCell class="text-right"> - </TableCell>
              </TableRow>
              <TableRow>
                <TableCell>
                  <div class="font-medium">@halk1337</div>
                </TableCell>
                <TableCell class="hidden xl:table-cell"> jasonstatham@gmail.com </TableCell>
                <TableCell class="xl:table-cell">
                  <Badge class="text-xs" variant="default"> done </Badge>
                </TableCell>
                <TableCell class="hidden md:table-cell lg:hidden xl:table-cell">
                  2023-06-23, 18:23
                </TableCell>
                <TableCell class="text-right"> 35 € </TableCell>
              </TableRow>
            </TableBody>
          </Table>
        </CardContent>
      </Card>
      <Card>
        <CardHeader>
          <CardTitle>ТОП Воркеров</CardTitle>
        </CardHeader>
        <CardContent class="grid gap-4">
          <div class="flex items-center gap-4 border-b pb-4">
            <Avatar class="hidden h-9 w-9 sm:flex">
              <!-- <AvatarImage src="/avatars/01.png" alt="Avatar" /> -->
              <AvatarFallback>OM</AvatarFallback>
            </Avatar>
            <div class="grid gap-1">
              <p class="text-sm font-medium leading-none">Alexandr</p>
              <p class="text-sm text-muted-foreground">@alex_x15</p>
            </div>
            <div class="ml-auto font-medium">380 €</div>
          </div>
          <div class="flex items-center gap-4 border-b pb-4">
            <Avatar class="hidden h-9 w-9 sm:flex">
              <!-- <AvatarImage src="/avatars/01.png" alt="Avatar" /> -->
              <AvatarFallback>OM</AvatarFallback>
            </Avatar>
            <div class="grid gap-1">
              <p class="text-sm font-medium leading-none">Alexandr</p>
              <p class="text-sm text-muted-foreground">@alex_x15</p>
            </div>
            <div class="ml-auto font-medium">380 €</div>
          </div>
          <div class="flex items-center gap-4">
            <Avatar class="hidden h-9 w-9 sm:flex">
              <!-- <AvatarImage src="/avatars/01.png" alt="Avatar" /> -->
              <AvatarFallback>OM</AvatarFallback>
            </Avatar>
            <div class="grid gap-1">
              <p class="text-sm font-medium leading-none">Alexandr</p>
              <p class="text-sm text-muted-foreground">@alex_x15</p>
            </div>
            <div class="ml-auto font-medium">250 €</div>
          </div>
        </CardContent>
      </Card>
    </div>
  </main>
</template>

<style></style>