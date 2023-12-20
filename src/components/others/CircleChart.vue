<template>
    <div>
      <canvas ref="circleChart"></canvas>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        chart: null,
        data: {
          labels: ['Red', 'Blue', 'Yellow'],
          datasets: [
            {
              data: [300, 50, 100],
              backgroundColor: ['rgb(255, 99, 132)', 'rgb(54, 162, 235)', 'rgb(255, 255, 0)'],
            },
          ],
        },
      };
    },
    mounted() {
      this.renderChart();
    },
    methods: {
      renderChart() {
        const ctx = this.$refs.circleChart.getContext('2d');
        this.chart = new window.Chart(ctx, {
          type: 'doughnut',
          data: this.data,
        });
      },
    },
  };
  </script>
