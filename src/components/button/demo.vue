<template>
  <Demo-block title="Button 按钮" subtitle="基础的按钮用法。" :README="README">
    <Demo-row title="不同尺寸" description="默认设定四个尺寸的按钮，通过size来区分" :code="example1">
      <j-button class="btn" size="mini">超小按钮</j-button>
      <j-button class="btn" size="small">小型按钮</j-button>
      <j-button class="btn" size="medium">默认按钮</j-button>
      <j-button class="btn" size="large">大型按钮</j-button>
    </Demo-row>

    <Demo-row title="插入不同图标" description="可通过slot插入不同的icon、html等内容" :code="example2">
      <j-button class="btn">
        <j-icon name="done"/>确定
      </j-button>
      <j-button class="btn">
        <j-icon name="pets"/>确定
      </j-button>
      <j-button class="btn">
        <j-icon name="search"/>确定
      </j-button>
    </Demo-row>

    <Demo-row title="不同类型" description="默认五种类型的按钮，普通、成功、警告、错误、文字" :code="example3">
      <j-button class="btn" type="primary" @click="handleClick">primary</j-button>
      <j-button class="btn" type="success">success</j-button>
      <j-button class="btn" type="warning">warning</j-button>
      <j-button class="btn" type="error">error</j-button>
      <j-button class="btn" type="text">{{ test }}</j-button>
    </Demo-row>

    <Demo-row title="禁用状态" description="不可点击，禁用状态下的按钮" :code="example4">
      <j-button class="btn" type="primary" disabled>primary</j-button>
      <j-button class="btn" type="success" disabled>success</j-button>
      <j-button class="btn" type="warning" disabled>warning</j-button>
      <j-button class="btn" type="error" disabled>error</j-button>
      <j-button class="btn" type="text" disabled>文字按钮</j-button>
    </Demo-row>
  </Demo-block>
</template>

<script>
import DemoCommon from "../common/demo-common";
import README from "./README.md";

export default {
  mixins: [DemoCommon],
  data() {
    return {
      nodeList: [],

      README
    };
  },
  computed: {
    test() {
        // console.log('getter!s', this.$store.getters.total)
        return this.$store.getters.total
    },
    example1() {
      return `<j-button class="btn" size="mini">超小按钮</j-button>
<j-button class="btn" size="small">小型按钮</j-button>
<j-button class="btn" size="medium">默认按钮</j-button>
<j-button class="btn" size="large">大型按钮</j-button>`;
    },
    example2() {
      return `<j-button class="btn">
    <j-icon name="done"/>确定
</j-button>
<j-button class="btn">
    <j-icon name="pets"/>确定
</j-button>
<j-button class="btn">
    <j-icon name="search"/>确定
</j-button>`;
    },
    example3() {
      return `<j-button class="btn" type="primary" @click="handleClick">primary</j-button>
<j-button class="btn" type="success">success</j-button>
<j-button class="btn" type="warning">warning</j-button>
<j-button class="btn" type="error">error</j-button>
<j-button class="btn" type="text">文字按钮</j-button>`;
    },
    example4() {
      return `<j-button class="btn" type="primary" disabled>primary</j-button>
<j-button class="btn" type="success" disabled>success</j-button>
<j-button class="btn" type="warning" disabled>warning</j-button>
<j-button class="btn" type="error" disabled>error</j-button>
<j-button class="btn" type="text" disabled>文字按钮</j-button>`;
    }
  },
  methods: {
    handleClick(event) {
      this.$store.state.count += 100
      alert("button click");
    }
  }
};
</script>
<style lang="scss">
</style>
