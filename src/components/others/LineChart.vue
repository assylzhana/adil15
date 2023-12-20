<template>
  <div>
    <canvas ref="lineChart"></canvas>
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
            label: 'My Dataset',
            borderColor: 'rgb(75, 192, 192)',
            data: [65, 59, 80, 81, 56, 55, 40],
            fill: false,
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
      const ctx = this.$refs.lineChart.getContext('2d');
      this.chart = new window.Chart(ctx, {
        type: 'line',
        data: this.data,
      });
    },
  },
};
</script>
