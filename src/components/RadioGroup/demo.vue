<template>
  <Demo-block title="RadioGroup 单选框组" subtitle="在一组备选项中进行单选。" :README="README">
    <Demo-row title="基础用法" :description="`适用于在多个互斥的选项中选择的场景，当前选中值${value}`" :code="example1">
      <j-radio-group v-model="value">
        <j-radio :value="1">备选项</j-radio>
        <j-radio :value="2">备选项</j-radio>
      </j-radio-group>
    </Demo-row>

    <Demo-row title="单独使用Radio组件" :description="`适用少量互斥选项，当前选中值${otherValue}`" :code="example2">
      <j-radio v-model="otherValue" :value="1">
        <j-hover-tip type="right-center">
          <template slot="hover-part">あらがき ゆい</template>
          <template slot="tip-part">
            <img src="/static/img/gakki.jpg" style="width: 100px" alt="示意图">
          </template>
        </j-hover-tip>
      </j-radio>
      <j-radio v-model="otherValue" :value="2">
        <j-hover-tip type="right-center">
          <template slot="hover-part">石原さとみ</template>
          <template slot="tip-part">
            <img
              src="/static/img/u=4046980169,286278015&fm=26&gp=0.jpg"
              style="width: 100px"
              alt="示意图"
            >
          </template>
        </j-hover-tip>
      </j-radio>
    </Demo-row>

    <Demo-row title="禁用状态" description="单选框不可用的状态" :code="example3">
      <j-radio-group v-model="anotherValue">
        <j-radio :value="1">备选项</j-radio>
        <j-radio :value="2" disabled>备选项</j-radio>
      </j-radio-group>
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
      value: 1,
      otherValue: 1,
      anotherValue: 1,

      README
    };
  },
  computed: {
    example1() {
      return `<j-radio-group v-model="value">
    <j-radio :value="1">备选项</j-radio>
    <j-radio :value="2">备选项</j-radio>
</j-radio-group>`;
    },
    example2() {
      return `<j-radio v-model="otherValue" value="1">备选项</j-radio>
<j-radio v-model="otherValue" value="2">备选项</j-radio>`;
    },
    example3() {
      return `<j-radio-group v-model="anotherValue">
    <j-radio :value="1">备选项</j-radio>
    <j-radio :value="2" disabled>备选项</j-radio>
</j-radio-group>`;
    }
  }
};
</script>
<style lang="scss">
.demo-row {
  .row-item-subtitle {
    min-width: 100px;
  }
  .row-item {
    margin-top: 32px;
  }
  .slider-wrapper {
    max-width: 520px;
    flex: 1;
  }
}
</style>
