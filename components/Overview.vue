<script setup lang="ts">
import {
  VisAxis,
  VisStackedBar,
  VisXYContainer,
  VisSingleContainer,
  VisDonut,
  VisTooltip
} from '@unovis/vue'
import { Donut, StackedBar } from '@unovis/ts'
import { computed } from 'vue'
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card'

type Data = (typeof data)[number]
const data = [
  { name: 'Пн', fullName: 'Понедельник', total: 350 },
  { name: 'Вт', fullName: 'Вторник', total: 220 },
  { name: 'Ср', fullName: 'Среда', total: 839 },
  { name: 'Чт', fullName: 'Четверг', total: 255 },
  { name: 'Пт', fullName: 'Пятница', total: 350 },
  { name: 'Сб', fullName: 'Суббота', total: 225 },
  { name: 'Вс', fullName: 'Воскресенье', total: 563 }
]

const triggers = {
  [StackedBar.selectors.bar]: (d: any) =>
    `<span> ${d.fullName}: </span><span class="font-medium">${d.total} €</span>`
}

// type DonutData = typeof donutData[number]

const donutData = [
  { name: '@alex_x15', total: 23 },
  { name: '@first_name', total: 25 },
  { name: '@plastmas', total: 55 },
  { name: '@vadim', total: 81 }
]

const donutTriggers = {
  [Donut.selectors.segment]: (d: any) =>
    `<span>${d.data.name}</span> – <span class="font-medium">${d.data.total} €</span>`
}

const value = (d: { total: number }) => d.total

interface MobileBreakpoints {
  left: number
  right: number
}


const isMobile = computed<MobileBreakpoints>(() => {
    if (process.client) {
        return window.innerWidth <= 768 ? { left: 0, right: 0 } : { left: 20, right: 20 }
    } else {
        return { left: 0, right: 0 }
    }
})

</script>

<template>
  <div class="mt-4 grid grid-cols-1 gap-8 md:grid-cols-2 xl:gap-8">
    <Card>
      <CardHeader>
        <CardTitle> График заводов по дням </CardTitle>
      </CardHeader>
      <CardContent>
        <VisXYContainer height="300px" :margin="isMobile" :data="data">
          <VisStackedBar
            :x="(d: Data, i: number) => i"
            :y="(d: Data) => d.total"
            color="#41b883"
            :rounded-corners="5"
            :bar-padding="0.2"
          />
          <VisAxis
            type="x"
            :num-ticks="data.length"
            :tick-format="(index: number) => data[index]?.name"
            :grid-line="false"
            :tick-line="false"
            color="#888888"
          />
          <VisAxis
            type="y"
            :num-ticks="data.length"
            :tick-format="(index: number) => data[index]?.name"
            :grid-line="false"
            :tick-line="false"
            :domain-line="false"
            color="#888888"
          />
          <VisTooltip :triggers="triggers" />
        </VisXYContainer>
      </CardContent>
    </Card>
    <Card>
      <CardHeader>
        <CardTitle> Общая статистика по воркерам </CardTitle>
      </CardHeader>
      <CardContent>
        <VisSingleContainer :data="donutData">
          <VisTooltip :triggers="donutTriggers" />
          <VisDonut
            :value="value"
            :arcWidth="50"
            :cornerRadius="0"
            centralLabel="Заводы по воркерам"
            centralSubLabel="Общее по воркерам"
          />
        </VisSingleContainer>
      </CardContent>
    </Card>
  </div>
</template>
