<template>
  <div class="wrapper_pay">
    <div class="header"><label>Привязанные карты</label></div>
    <div class="content">
      <div class="list">
        <div class="item" v-for="card in cardsList" :key="card.id">
          <label>{{ card.name }}</label>
          <label>**** {{ card.number }}</label>
          <label v-if="card.main">Основная</label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PaymentsSettings",
  data() {
    return {
      cardsList: [
        {
          id: 1,
          name: "MasterCard",
          number: "1234",
          main: true,
        },
        {
          id: 2,
          name: "Visa",
          number: "0936",
          main: false,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.wrapper_pay {
  width: 95%;
  margin: 0 auto;
  .header {
    display: flex;
    justify-content: start;
    margin: 10px 0 20px;
  }
  .content {
    display: flex;
    align-items: start;
    margin-left: 10px;
    margin-bottom: 30px;
    .list {
      display: flex;
      flex-direction: column;
      gap: 15px;
      .item {
        display: flex;
        flex-direction: row;
        text-align: start;
        gap: 8px;
      }
    }
  }
}
</style>
