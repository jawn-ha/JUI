<template>
  <Demo-block title="Table 表格" subtitle="用于展示多条结构类似的数据，可对数据进行排序、筛选、对比或其他自定义操作" :README="README">
    <Demo-row title="基础用法" description="基础的表格展示用法" :code="example1">
      <j-table :data="tableData">
        <template slot-scope="{ item }">
          <j-table-column label="姓名">{{ item.name }}</j-table-column>

          <j-table-column label="日期">{{ item.date }}</j-table-column>

          <j-table-column label="地址">{{ item.address }}</j-table-column>
        </template>
      </j-table>
    </Demo-row>

    <Demo-row title="带斑马纹表格" description="使用带斑马纹的表格，可以更容易区分出不同行的数据" :code="example2">
      <j-table :data="tableData" stripe>
        <template slot-scope="{ item }">
          <j-table-column label="姓名">{{ item.name }}</j-table-column>

          <j-table-column label="日期">{{ item.date }}</j-table-column>

          <j-table-column label="地址">{{ item.address }}</j-table-column>
        </template>
      </j-table>
    </Demo-row>

    <Demo-row title="合并表头" description="合并某些相关项" :code="example2">
      <j-table :data="tableData" algin="center">
        <template slot-scope="{ item }">
          <j-table-column label="真实姓名以及出生日期">{{ item.name }}</j-table-column>

          <j-table-column label="真实姓名以及出生日期">{{ item.date }}</j-table-column>

          <j-table-column label="地址">{{ item.address }}</j-table-column>
        </template>
      </j-table>
    </Demo-row>

    <Demo-row title="自定义列模板" description="自定义列的显示内容，可组合其他组件使用" :code="example2">
      <j-table :data="tableData">
        <template slot-scope="{ item }">
          <j-table-column label="头像">
            <j-hover-tip type="right-center">
              <template slot="hover-part">{{ item.name }}</template>
              <template slot="tip-part">
                <img src="/static/img/gakki.jpg" alt="示意图">
              </template>
            </j-hover-tip>
          </j-table-column>

          <j-table-column label="地址">{{ item.address }}</j-table-column>

          <j-table-column label="操作">
            <j-button class="btn" type="primary" size="mini" @click="$message({ content: '编辑' })">编辑</j-button>
            <j-button class="btn" type="primary" size="mini" @click="$message({ content: '删除' })">删除</j-button>
          </j-table-column>
        </template>
      </j-table>
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
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        }
      ],

      README
    };
  },
  computed: {
    example1() {
      return `<j-table :data="tableData">
    <template slot-scope="{ item }">
        <j-table-column label="姓名">{{ item.name }}</j-table-column>

        <j-table-column label="日期">{{ item.date }}</j-table-column>

        <j-table-column label="地址">{{ item.address }}</j-table-column>
    </template>
</j-table>`;
    },
    example2() {
      return `<j-table :data="tableData" stripe>
    <template slot-scope="{ item }">
        <j-table-column label="姓名">{{ item.name }}</j-table-column>

        <j-table-column label="日期">{{ item.date }}</j-table-column>

        <j-table-column label="地址">{{ item.address }}</j-table-column>
    </template>
</j-table>`;
    }
  }
};
</script>
<style lang="scss">
</style>
