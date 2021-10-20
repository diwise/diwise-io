<!-- Please remove this file from your project -->
<template>
  <GChart type="ColumnChart" :data="chartData" :options="chartOptions" />
</template>
<script>
import { GChart } from 'vue-google-charts'
export default {
  components: {
    GChart,
  },
  data() {
    return {
      // Array will be automatically processed with visualization.arrayToDataTable function
      chartData: [
        ['Sensor', 'SA_1', 'SA_2', 'SA_3'],
        generateSensor('08:00'),
        generateSensor('09:00'),
        generateSensor('10:00'),
        generateSensor('11:00'),
        generateSensor('12:00'),
        generateSensor('13:00'),
        generateSensor('14:00'),
        generateSensor('15:00'),
        generateSensor('16:00'),
        generateSensor('17:00'),
        generateSensor('18:00'),
        generateSensor('19:00'),
        generateSensor('20:00'),
      ],
      chartOptions: {
        chart: {
          title: 'Company Performance',
          subtitle: 'Sales, Expenses, and Profit: 2014-2017',
        },
      },
    }
  },
}

function generateSensor(timestamp) {
  return [
    timestamp,
    generateTemperature(1, 10),
    generateTemperature(1, 10),
    generateTemperature(1, 10),
  ]
}

function generateTemperature(min, max) {
  return Math.floor(Math.random() * (max - min + 1) + min)
}
</script>