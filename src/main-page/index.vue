<template>
  <div class="main-page-wrapper">
    <div class="main-page" ref="main-page"></div>
  </div>
</template>

<script>
export default {
  created() {
    let material = new Blotter.SlidingDoorMaterial();
    let text = new Blotter.Text("JUI", {
      family: "serif",
      size: 120,
      fill: "#171717"
    });
    let blotter = new Blotter(material, { texts: text });
    let scope = blotter.forText(text);

    this.$nextTick(() => {
      scope.appendTo(this.$refs["main-page"]);
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.main-page-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;

  .main-page {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}
</style>
