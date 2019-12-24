<script>
import { Bar } from "vue-chartjs";

export default {
  extends: Bar,
  name: "chart",
  data() {
    return {
      data: {
        labels: ["1", "2", "3"],
        datasets: [
          {
            data: [10, 20, 80],
            backgroundColor: [
              "rgba(255, 99, 132, 0.3)",
              "rgba(54, 162, 235, 0.3)",
              "rgba(255, 206, 86, 0.3)"
            ],
            borderWidth: 1
          },
          {
            data: [30, 10, 20],
            backgroundColor: [
              "rgba(255, 99, 32, 0.3)",
              "rgba(54, 122, 125, 0.3)",
              "rgba(225, 106, 86, 0.3)"
            ],
            borderWidth: 1
          }
        ]
      },
      options: {
        padding: 80,
        legend: false,
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          xAxes: [
            {
              stacked: true,
              categoryPercentage: 0.5,
              barPercentage: 1
            }
          ],
          yAxes: [
            {
              stacked: true,
              ticks: {
                beginAtZero: true,
                min: 0,
                max: 150
              }
            }
          ]
        }
      }
    };
  },
  mounted() {
    this.renderChart(this.data, this.options);
  }
};
</script>