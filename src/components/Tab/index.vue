<template>
  <transition name="move">
    <div v-if="isOpen">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    label: { type: String, required: true },
    id: { type: [String, Number], required: true },
    disabled: { type: Boolean, default: false },
    closable: { type: Boolean, default: false }
  },
  computed: {
    isOpen() {
      return this.jTabs.activeId === this.id;
    }
  },
  inject: ["jTabs"],
  created() {
    this.jTabs.childrens.push(this);
  },
  destroyed() {
    this.jTabs.childrens = this.jTabs.childrens.filter(
      item => item.id !== this.id
    );
  }
};
</script>
<style lang="scss">
</style>
