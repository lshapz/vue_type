<template>
    <div>
        <h2>Vue (D3) - TS</h2>
        <div id="chartDiv">
            <D3PieChart :dataModel="pieData" />
        </div>
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
      @Prop() private pieData!: object;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#chartDiv {
    height: 500px;
    width: 500px;
}


</style>
