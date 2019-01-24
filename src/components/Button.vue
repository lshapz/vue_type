<template>
  <button @click="changeData">Change Things</button>
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

</style>
