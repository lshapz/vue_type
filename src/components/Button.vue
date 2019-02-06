<template>
  <button class="changeBtn" @click="changeData">Change Things</button>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component({})
export default class Button extends Vue {
  @Prop() private msg!: string;
  @Prop() private changeData!: void;

  private doChange(): void {
    console.log('button click');
  }
}
</script>
<style>
.changeBtn {
  font-size: 150%;
  padding: .5em 1em;
  border: transparent;
  background-color: rgba(230, 230, 230, 0.851);
  text-decoration: none;
  border-radius: 5px;
  cursor: pointer;
}

.changeBtn:active {
  box-shadow: 5px 10px grey;
}

</style>
