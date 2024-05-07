<script setup>
import Chart from 'chart.js/auto';

const labels = [
  'Januari',
  'Februari',
  'March',
  'April',
  'May',
  'June',
  'july',
  'augst',
  'september',
  'october',
  'november',
  'december',
];

const data = {
  labels: labels,
  datasets: [{
    label: 'My First dataset',
    backgroundColor: 'rgb(255, 99, 132)',
    borderColor: 'rgb(255, 99, 132)',
    data: [25, 35, 15, 10, 23, 51, 54, 33, 21, 10, 15, 50],
  }]
};

const config = {
  type: 'bar',
  data: data,
  Options: {}
}

onMounted(() => {
  const myChart = new Chart(
    document.getElementById('myChart'),
    config
  );
})
</script>

<template>
  <div>
    <canvas id="myChart"></canvas>
  </div>
</template>



 
