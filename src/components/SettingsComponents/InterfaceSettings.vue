<template>
  <div class="wrapper_interface">
    <div class="content">
      <div class="set">
        <input type="checkbox" />
        <label>Темная тема</label>
      </div>
      <div class="set">
        <input type="checkbox" />
        <label>Широкоформатный монитор</label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InterfaceSettings",
};
</script>

<style lang="scss" scoped>
.wrapper_interface {
  width: 95%;
  margin: 0 auto;
  .content {
    display: flex;
    flex-direction: row;
    gap: 15px;
    align-items: start;
    margin: 10px 0 20px;
    margin-left: 10px;
    .set {
      width: calc(50% - 10px);
      display: flex;
      flex-direction: row;
      gap: 5px;
    }
  }
}
</style>
