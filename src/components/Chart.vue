<template>
<div id="chartDiv">

  <D3PieChart :dataModel="pieData" />

</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import { D3PieChart } from 'jscatalyst';
@Component({
    // props: {
    //     msg: String
    // }
    components: {
        D3PieChart,
    },
})
export default class Chart extends Vue {
      @Prop() private msg!: string;
      @Prop() private pieData!: object;


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#chartDiv {
    height: 750px;
    width: 750px;
    margin: 0 auto;
    padding-top: 50px;

}
</style>
