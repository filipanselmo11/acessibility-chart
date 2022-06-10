<template>
  <div id="container"></div>
</template>

<script>
import Highcharts from "highcharts";
import Accessibility from "highcharts/modules/accessibility";
Accessibility(Highcharts);
export default {
  name: "HelloWorld",
  data: () => ({}),
  mounted() {
    this.dataSource();
  },
  methods: {
    async dataSource() {
      Highcharts.chart("container", {
        title: {
          text: "Crescimento do Emprego Solar por Setor, 2010-2016",
        },
        accessibility: {
          typeDescription: "Gráfico de 5 linhas",
        },

        subtitle: {
          text: "Fonte: thesolarfoundation.com",
        },

        yAxis: {
          title: {
            text: "Numero de Empregados",
          },
          accessibility: {
            description: "Numero de Empregados",
          },
        },

        xAxis: {
          accessibility: {
            enabled: true,
            description: 'Dados do Eixo X',
            rangeDescription: "Faixa: 2010 a 2017",
          },
        },

        legend: {
          layout: "vertical",
          align: "right",
          verticalAlign: "middle",
        },

        plotOptions: {
          series: {
            label: {
              connectorAllowed: false,
            },
            pointStart: 2010,
          },
        },

        series: [
          {
            name: "Instalação",
            data: [43934, 52503, 57177, 69658, 97031, 119931, 137133, 154175],
          },
          {
            name: "Manufatura",
            data: [24916, 24064, 29742, 29851, 32490, 30282, 38121, 40434],
          },
          {
            name: "Vendas & Distribuição",
            data: [11744, 17722, 16005, 19771, 20185, 24377, 32147, 39387],
          },
          {
            name: "Desenvolvimento do Projeto",
            data: [null, null, 7988, 12169, 15112, 22452, 34400, 34227],
          },
          {
            name: "Outro",
            data: [12908, 5948, 8105, 11248, 8989, 11816, 18274, 18111],
          },
        ],

        responsive: {
          rules: [
            {
              condition: {
                maxWidth: 500,
              },
              chartOptions: {
                legend: {
                  layout: "horizontal",
                  align: "center",
                  verticalAlign: "bottom",
                },
              },
            },
          ],
        },
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
