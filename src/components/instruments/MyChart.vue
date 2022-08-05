<template>
  <div class="chart__filters">
    <div>
      <SubcategorySelect
        class="chart__select"
        v-model="selectedSort"
        :options="sortOptions"
      />
    </div>
    <div class="chart__filters__right">
      <div class="chart__filters__smart">
        <input type='checkbox' class='ios8-switch' id='checkbox-1'>
        <label class="smart-label" for='checkbox-1'>Умный масштаб</label>
      </div>
      <div class="chart__export">
        <div>
          <svg width="22" height="22" viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M13.9645 10.2588L11 13.2234L8.0354 10.2588" stroke="#3872F9" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M11 4.33105V13.2239" stroke="#3872F9" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M18.4195 14.7051C18.4195 14.2909 18.0837 13.9551 17.6695 13.9551C17.2552 13.9551 16.9195 14.2909 16.9195 14.7051H18.4195ZM5.08057 14.7051C5.08057 14.2909 4.74478 13.9551 4.33057 13.9551C3.91635 13.9551 3.58057 14.2909 3.58057 14.7051H5.08057ZM16.9195 14.7051C16.9195 15.9282 15.928 16.9196 14.7049 16.9196V18.4196C16.7564 18.4196 18.4195 16.7566 18.4195 14.7051H16.9195ZM14.7049 16.9196H7.29513V18.4196H14.7049V16.9196ZM7.29513 16.9196C6.07206 16.9196 5.08057 15.9282 5.08057 14.7051H3.58057C3.58057 16.7566 5.24364 18.4196 7.29513 18.4196V16.9196Z" fill="#3872F9"/>
          </svg>
        </div>
        <div class="chart__export__text">
          Экспорт
        </div>
      </div>
    </div>
  </div>
  <div id="chart" class="chart">
  <apexchart
    type="area"
    height="350"
    :options="chartOptions"
    :series="sortedSeries"
  >
  </apexchart>
</div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";
import SubcategorySelect from '@/components/SubcategorySelect'

let close =
  '<svg style="margin-left: 6px" width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">\n' +
  '<rect width="20" height="20" rx="10" fill="#F5F7FA"/>\n' +
  '<path d="M7 7L13 13M13 7L7 13" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>\n' +
  '</svg>'

export default {
  name: "Chart",
  components: {
    apexchart: VueApexCharts,
    SubcategorySelect
  },
  data: function () {
    return {
      series: [
        {
          name: 'mysite.com',
          data: [31, 40, 28, 51, 42, 109, 100, 40, 60, 30, 20, 12, 70],
          color:'#F34C2A'
        },
        {
          name: 'kinopoisk.ru',
          data: [11, 32, 45, 32, 34, 52, 41, 40, 28, 51, 42, 109, 12],
          color:'#4BB574',
        },
        {
          name: 'ivi.ru',
          data: [11, 50, 45, 10, 8, 90, 41, 90, 45, 20, 17, 100, 26.55],
          color: '#3872F9'
        },
        {
          name: 'vokrug.tv',
          data: [20, 90, 45, 20, 17, 100, 11, 22, 50, 45, 40, 90, 50],
          color:'#FFD02F',
        },
        {
          name: 'film.ru',
          data: [16, 57, 90, 10, 0, 10, 51, 48, 14, 30, 60, 81, 50],
          color: '#1E4B95',
        },
        {
          name: 'afisha.ru',
          data: [22, 50, 45, 40, 90, 40, 41, 50, 45, 40, 90, 40, 40],
          color: '#8562F9',
        },
        {
          name: 'megogo.net',
          data: [31, 50, 12, 50, 40, 20, 51, 31, 50, 12, 50, 40, 22],
          color: '#D96D6E',
        },
        {
          name: 'more.tv',
          data: [40, 50, 48, 14, 30, 60, 81, 65, 10, 100, 0, 31, 100],
          color: '#896E0F',
        },
        {
          name: 'okko.tv',
          data: [30, 50, 30, 10, 4, 60, 21, 1, 10, 65, 10, 100, 5],
          color: '#357F51',
        },
        {
          name: 'wink.ru',
          data: [1, 10, 65, 10, 100, 0, 31, 10, 4, 60, 21, 1, 9],
          color: '#AA351D',

        },
      ],
      chartOptions: {
        chart: {
          type: 'area',
          toolbar: {
            show: false
          },
        },
        dataLabels: {
          enabled: false
        },
        stroke: {
          curve: 'smooth',
          width: 2,
        },
        legend: {
          position: 'top',
          horizontalAlign: 'left',
          fontSize: '12px',
          fontFamily: 'Commissioner',
          fontWeight: 400,
          height: '18px',
          markers: {
            width: 7.2,
            height: 7.2,
          },
          formatter: function(val, opts) {
            return [val, close]
          },
        },
        yaxis: {
          labels: {
            style: {
              fontFamily: 'Commissioner',
              fontStyle: 'normal',
              fontWeight: 400,
              fontSize: '10px',
              lineHeight: '16px',
              color: '#65676D',
            }
          }
        },
        xaxis: {
          type: 'date',
          categories: [
            "07.03.21",
            "08.03.21",
            "09.03.21",
            "10.03.21",
            "11.03.21",
            "12.03.21",
            "13.03.21",
            "14.03.21",
            "15.03.21",
            "16.03.21",
            "17.03.21",
            "18.03.21",
            ""
          ],
          labels: {
            formatter: function(value, timestamp, opts) {
              return value
            },
            style: {
              fontFamily: 'Commissioner',
              fontStyle: 'normal',
              fontWeight: 400,
              fontSize: '10px',
              lineHeight: '16px',
              color: '#65676D',
              cssClass: 'apexcharts-xaxis-label',
            },
          }
        },
        tooltip: {
          x: {
            format: 'dd.MM.yy'
          },
        },
        /*xaxis: {
          type: 'datetime',
          categories: [
            "2018-09-19T00:00:00.000Z",
            "2018-09-19T01:30:00.000Z",
            "2018-09-19T02:30:00.000Z",
            "2018-09-19T03:30:00.000Z",
            "2018-09-19T04:30:00.000Z",
            "2018-09-19T05:30:00.000Z",
            "2018-09-19T06:30:00.000Z",
            "2018-09-19T07:00:00.000Z",
            "2018-09-19T08:30:00.000Z",
            "2018-09-19T09:30:00.000Z",
            "2018-09-19T10:30:00.000Z",
            "2018-09-19T11:30:00.000Z",
            "2018-09-19T12:30:00.000Z",
          ]
        },
        tooltip: {
          x: {
            format: 'dd/MM/yy HH:mm'
          },
        },*/
      },
      selectedSort: 10,
      sortOptions: [
        {
          id: 0,
          name: 'Конкуренты: 2(min)',
          value: 2,
        },
        {
          id: 1,
          name: 'Конкуренты: 3',
          value: 3,
        },
        {
          id: 2,
          name: 'Конкуренты: 4',
          value: 4,
        },
        {
          id: 3,
          name: 'Конкуренты: 5',
          value: 5,
        },
        {
          id: 4,
          name: 'Конкуренты: 6',
          value: 6,
        },
        {
          id: 5,
          name: 'Конкуренты: 7',
          value: 7,
        },
        {
          id: 6,
          name: 'Конкуренты: 8',
          value: 8,
        },
        {
          id: 7,
          name: 'Конкуренты: 9',
          value: 9,
        },
        {
          id: 8,
          name: 'Конкуренты: 10(max)',
          value: 10,
        },
      ],
    }
  },
  computed: {
    sortedSeries () {
      return [...this.series].slice(0,this.selectedSort)
    },
  },
};
</script>
<style lang="scss">
.chart__filters {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin: 24px 16px;
  gap: 24px;

  height: 36px;


  /* Inside auto layout */

  flex: none;
  order: 1;
  align-self: stretch;
  flex-grow: 0;
  z-index: 3;
}
.chart__export {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 8px;
  gap: 8px;
  flex-direction: row;
  font-family: 'Commissioner';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  height: 36px;
  width: 127px;
  border: 1px solid #E7E9F1;
  border-radius: 16px;
  background: #f1f5fe;
  .chart__export__text{
    color: #3872F9;
    opacity: 1;
    display: flex;
    flex-direction: row;
  }
  .chart__export__text::after{
    content: url("data:image/svg+xml,%3Csvg width='10' height='6' viewBox='0 0 10 6' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M5 5.33301L10 0.333008L-2.18557e-07 0.333008L5 5.33301Z' fill='%233872F9'/%3E%3C/svg%3E%0A");
    margin-left: 13px;
  }
}
.chart__select {
  border: 1px solid #E7E9F1 !important;
  border-radius: 8px !important;
  font-weight: 400 !important;
  font-size: 14px !important;
  line-height: 20px !important;
  color: #1A1A1B !important;
  background: white !important;
  width: 200px !important;
  height: 36px !important;
  padding: 8px !important;
}
.chart {
    width: 100%;
    height: max-content;
    margin-right: 16px;
    margin-top: 0px !important;
}
.apexcharts-inner {
  width: 100%;
}
.apexcharts-legend {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  padding: 0px;
  gap: 8px;
  /* Inside auto layout */

  flex: none;
  order: 2;
  flex-grow: 0;
  z-index: 2;
}
.apexcharts-legend-series{
  box-sizing: border-box;

  /* Auto layout */

  display: flex !important;
  flex-direction: row;
  align-items: center;
  padding: 4px !important;
  gap: 6px;
  isolation: isolate;
  height: 26px;
  margin: 0 !important;


  /* White */

  background: #FFFFFF;
  /* Grey/G-10 */

  border: 1px solid #E7E9F1;
  border-radius: 100px;

  /* Inside auto layout */

  flex: none;
  order: 5;
  flex-grow: 0;

}
.apexcharts-legend-text {
  font-family: 'Commissioner';
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 18px;
  /* identical to box height, or 150% */

  display: flex;
  align-items: center;

  /* Black */

  color: #1A1A1B;


  /* Inside auto layout */

  flex: none;
  order: 1;
  flex-grow: 0;

}
.apexcharts-tooltip {
  display: grid;
  flex-direction: column;
  align-items: flex-start;
  padding: 8px 12px;
  gap: 4px;

  position: absolute;
  width: 163px;
  height: min-content;
  left: 25px;
  top: 0px;

  /* White */

  background: #FFFFFF;
  /* Shadows/Dropdown */

  box-shadow: 0px 12px 36px rgba(58, 62, 71, 0.15);
  border-radius: 8px;
  border: transparent !important;
  .apexcharts-tooltip-series-group{
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 0px;
    gap: 6px;

    width: 139px;
    height: 18px;


    /* Inside auto layout */

    flex: none;
    order: 0;
    flex-grow: 0;
    position: relative;
    .apexcharts-tooltip-marker{
      width: 12px !important;
      height: 12px !important;
      margin-right: 0 !important;
    }
    .apexcharts-tooltip-text{
      height: 12px !important;
      width: 100px !important;

      /* Bold/B-12 */

      font-family: 'Commissioner' !important;
      font-style: normal;
      font-weight: 600;
      font-size: 12px !important;
      line-height: 18px;
      /* identical to box height, or 150% */

      display: flex;
      align-items: center;

      /* Black */

      color: #1A1A1B;


      /* Inside auto layout */

      flex: none;
      order: 1;
      flex-grow: 0;
      margin-bottom: auto;
      .apexcharts-tooltip-y-group {
        padding: 0px !important;
        display: flex;
        flex-direction: row;
        gap: 10px;
          .apexcharts-tooltip-text-y-label {
            width: 68px !important;
          }
          .apexcharts-tooltip-text-y-value{
            width: 43px !important;
          }
          .apexcharts-tooltip-text-y-value::after{
            content: "%";
          }
      }
    }
  }
  .apexcharts-tooltip-series-group:nth-of-type(2){
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 0px;
    gap: 6px;
    margin-top: 4px;

    width: 139px;
    height: 18px;
    border-bottom: 1px solid #E7E9F1;


    /* Inside auto layout */

    flex: none;
    order: 0;
    flex-grow: 0;
    position: relative;
    .apexcharts-tooltip-marker{
      width: 12px !important;
      height: 12px !important;
      margin-right: 0 !important;
    }
    .apexcharts-tooltip-text{
      width: 68px !important;
      height: 12px !important;

      /* Bold/B-12 */

      font-family: 'Commissioner' !important;
      font-style: normal;
      font-weight: 600;
      font-size: 12px !important;
      line-height: 18px;
      /* identical to box height, or 150% */

      display: flex;
      align-items: center;

      /* Black */

      color: #1A1A1B;


      /* Inside auto layout */

      flex: none;
      order: 1;
      flex-grow: 0;
      margin-bottom: auto;
      .apexcharts-tooltip-y-group {
        padding: 0px !important;
        display: flex;
        flex-direction: row;
        gap: 10px;
        .apexcharts-tooltip-text-y-label {
          width: 68px !important;
        }
        .apexcharts-tooltip-text-y-value{
          width: 43px !important;
        }
      }
    }
  }
  .apexcharts-tooltip-title {
    width: 45px;
    height: 18px;
    padding: 0px !important;

    /* Bold/B-12 */

    font-family: 'Commissioner';
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 18px;
    /* identical to box height, or 150% */

    display: flex;
    align-items: center;

    /* Black */

    color: #1A1A1B;


    /* Inside auto layout */

    flex: none;
    order: 0;
    flex-grow: 0;
    background: white !important;
    border: none !important;
  }
}
.apexcharts-xaxis-label{
  width: 40px;
  height: 40px;
  background-image: url("data:image/svg+xml,%3Csvg width='20' height='20' viewBox='0 0 20 20' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Crect width='20' height='20' rx='10' fill='%23F5F7FA'/%3E%3Cpath d='M7 7L13 13M13 7L7 13' stroke='%2384868C' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E") !important;
}
input[type="checkbox"].ios8-switch {
  position: absolute;
  margin: 8px 0 0 16px;
}
input[type="checkbox"].ios8-switch + label {
  position: relative;
  padding: 5px 0 0 50px;
  line-height: 2.0em;
}
input[type="checkbox"].ios8-switch + label:before {
  content: "";
  position: absolute;
  display: block;
  left: 0;
  top: 0;
  width: 32px; /* x*5 */
  height: 20px; /* x*3 */
  border-radius: 1000px; /* x*2 */
  background: #E7E9F1;
  border: 1px solid #d9d9d9;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
}
input[type="checkbox"].ios8-switch + label:after {
  content: "";
  position: absolute;
  display: block;
  left: 0px;
  top: 0px;
  width: 12px; /* x*3 */
  height: 12px; /* x*3 */
  border-radius: 16px; /* x*2 */
  background: #fff;
  border: 1px solid #d9d9d9;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  margin-top: 4px;
  margin-left: 4px;
}
input[type="checkbox"].ios8-switch + label:hover:after {
}
input[type="checkbox"].ios8-switch:checked + label:after {
  margin-left: 16px;
}
input[type="checkbox"].ios8-switch:checked + label:before {
  background: #55D069;
}
.smart-label{
  font-family: 'Commissioner';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  /* identical to box height, or 143% */


  /* Black */

  color: #1A1A1B;


  /* Inside auto layout */

  flex: none;
  order: 1;
  flex-grow: 0;
}
.chart__filters__right{
  display: flex;
  flex-direction: row;
  gap: 24px;
  align-items: center;
}
</style>
