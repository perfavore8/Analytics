<template>
  <div class="wrapper_tariff">
    <div class="header"><label>Тариф</label></div>
    <div class="content">
      <label>Текущий тариф: {{ currentTariff }}</label>
      <button>Изменить</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TariffSettings",
  data() {
    return {
      currentTariff: "Предприятие",
    };
  },
};
</script>

<style lang="scss" scoped>
.wrapper_tariff {
  width: 95%;
  margin: 0 auto;
  .header {
    display: flex;
    justify-content: start;
    margin: 10px 0 20px;
  }
  .content {
    display: flex;
    gap: 15px;
    align-items: start;
    margin-left: 10px;
    margin-bottom: 30px;
  }
}
</style>
