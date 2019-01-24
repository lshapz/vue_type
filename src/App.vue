<template>
  <div id="app">
    <Button :changeData="changeData" />
    <Chart :pieData="pieData" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Button from './components/Button.vue';
import Chart from './components/Chart.vue';

@Component({
  components: {
    Button,
    Chart,
  },
})
export default class App extends Vue {

  public pieData = [
    {label: 'Auto', value: 46}, {label: 'Architect', value: 57},
    {label: 'Agent', value: 44}, {label: 'Cambridge', value: 56},
    {label: 'Markets', value: 48}, {label: 'Canterbury', value: 57},
    {label: 'Cotton', value: 52}, {label: 'Granite', value: 47}, {label: 'Gloves', value: 53},
    {label: 'Planner', value: 40},
  ];

  public randomNumber() {
    return Math.floor(Math.random() * 50);
  }

  public changeData() {
    this.pieData = this.pieData.map( (item) => {
      item.value = this.randomNumber();
      return item;
    });
    console.table(this.pieData);
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
