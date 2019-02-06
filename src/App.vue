<template>
  <div id="app">
    <h1> Vue App with Angular Component In It </h1> 
    <div class="flexbox-container">
      <Button :changeData="changeData" />
      <Chart :pieData="pieData" />
      <bar-chart :strdatamodel='strdatamodel'></bar-chart>
    </div>
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
    {label: 'Cotton', value: 52}, {label: 'Granite', value: 47}, 
    {label: 'Gloves', value: 53}, {label: 'Planner', value: 40},
  ];

  public randomNumber() {
    return Math.floor(Math.random() * 53) + 3;
  }

  public changeData() {
    this.pieData = this.pieData.map( (item) => {
      item.value = this.randomNumber();
      return item;
    });
  }

  get strdatamodel() {
    const data = this.pieData.map((item) => {
      return {x: item.label, y: item.value};
    });
    return JSON.stringify(data);
  }

}
</script>

<style>

.flexbox-container {
  margin-top: 10%;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}

h1, h2 {
  text-align: center;
}

</style>
