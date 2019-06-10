<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"
      :num="6666"
      @reset="resetMsg" />
    <h1 @click="handleClick($event, '666')">{{computedMsg}}</h1>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import test from "./test";

@Component({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {
  private msg: string = "Hello, World!";

  get computedMsg(): string {
    return this.msg + "7777";
  }

  beforeCreate() {
    test.$alert("haha");
  }

  handleClick(event: object, name: string) {
    this.msg = "666";
    // console.log(event, name);
  }

  resetMsg(data: any) {
    console.log(data, "父组件收到啦");
  }
}
</script>
