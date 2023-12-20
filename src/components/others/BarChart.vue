<template>
    <div>
      <canvas ref="barChart"></canvas>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        chart: null,
        data: {
          labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
          datasets: [
            {
              label: 'My Bar Dataset',
              backgroundColor: 'rgb(75, 192, 192)',
              data: [65, 59, 80, 81, 56, 55, 40],
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
        const ctx = this.$refs.barChart.getContext('2d');
        this.chart = new window.Chart(ctx, {
          type: 'bar',
          data: this.data,
        });
      },
    },
  };
  </script>
  
