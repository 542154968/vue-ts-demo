<template>
  <div class="hello"
    @click="resetMsg({name: 'lqk'})">
    {{num}}
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Emit } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  @Prop({ default: 6, type: Number })
  private num!: number;
  count: number = 0;

  @Emit("reset")
  resetMsg(data: object) {
    console.log("父组件收到没");
  }
}
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
