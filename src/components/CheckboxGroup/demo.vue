<template>
  <Demo-block title="CheckBox 多选框组" subtitle="在一组备选项中进行多选。" :README="README">
    <Demo-row title="基础用法" :description="`单独使用可以表示两种状态之间的切换，当前选中值${value}`" :code="example1">
      <j-checkbox v-model="value" :value="1">备选项</j-checkbox>
    </Demo-row>

    <Demo-row title="禁用状态" :description="`多选框不可用状态`" :code="example1">
      <j-checkbox v-model="value" :value="1" disabled>备选项</j-checkbox>
    </Demo-row>

    <Demo-row
      class="checkbox-group-box"
      title="多选框组"
      :description="`多选框不可用状态，选中项${anotherValue}`"
      :code="example1"
    >
      <j-checkbox-group v-model="anotherValue">
        <j-checkbox value="あらがき ゆい">
          <j-hover-tip type="right-center">
            <template slot="hover-part">あらがき ゆい</template>
            <template slot="tip-part">
              <img src="/static/img/gakki.jpg" style="width: 100px" alt="示意图">
            </template>
          </j-hover-tip>
        </j-checkbox>
        <j-checkbox value="石原さとみ">
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
        </j-checkbox>
        <j-button size="mini" @click.stop="anotherValue = ['石原さとみ','あらがき ゆい']">全都要</j-button>
      </j-checkbox-group>
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
      value: true,
      otherValue: 1,
      anotherValue: [],

      README
    };
  },
  computed: {
    example1() {
      return `<j-checkbox v-model="value" :value="1">备选项</j-checkbox>`;
    },
    example2() {
      return `<j-checkbox v-model="value" :value="1" disabled>备选项</j-checkbox>`;
    },
    example3() {
      return `<j-checkbox-group v-model="anotherValue">
    <j-checkbox :value="1">备选项1</j-checkbox>
    <j-checkbox :value="2">备选项2</j-checkbox>
</j-checkbox-group>`;
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

  &.checkbox-group-box {
    .checkbox-item {
      margin-right: 8px;
    }
  }
}
</style>
