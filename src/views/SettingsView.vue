<template>
  <div class="wrapper">
    <div class="container">
      <div class="header"><label>Настройки</label></div>
      <nav>
        <button
          @click="currentPage = 1"
          :class="{ active_page: currentPage == 1 }"
        >
          Аккаунт
        </button>
        <button
          @click="currentPage = 2"
          :class="{ active_page: currentPage == 2 }"
        >
          Платежи
        </button>
        <button
          @click="currentPage = 3"
          :class="{ active_page: currentPage == 3 }"
        >
          Тариф
        </button>
        <button
          @click="currentPage = 4"
          :class="{ active_page: currentPage == 4 }"
        >
          Интерфейс
        </button>
      </nav>
      <div class="content">
        <AccountSettings v-if="currentPage == 1" />
        <PaymentsSettings v-if="currentPage == 2" />
        <TariffSettings v-if="currentPage == 3" />
        <InterfaceSettings v-if="currentPage == 4" />
      </div>
    </div>
  </div>
</template>

<script>
import TariffSettings from "@/components/SettingsComponents/TariffSettings.vue";
import AccountSettings from "@/components/SettingsComponents/AccountSettings.vue";
import InterfaceSettings from "@/components/SettingsComponents/InterfaceSettings.vue";
import PaymentsSettings from "@/components/SettingsComponents/PaymentsSettings.vue";
export default {
  name: "SettingsView",
  components: {
    AccountSettings,
    PaymentsSettings,
    TariffSettings,
    InterfaceSettings,
  },
  data() {
    return {
      currentPage: 3,
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.wrapper {
  width: 100%;
  .container {
    display: flex;
    flex-direction: column;
    align-items: start;
    margin: 20px auto;
    width: 90%;
    .header {
      margin-bottom: 20px;
    }
    nav {
      width: 95%;
      background-color: rgba(233, 233, 233, 0.547);
      display: flex;
      flex-direction: row;
      gap: 5px;
      padding: 15px 2.5%;
      button {
        width: 100px;
        height: 24px;
        outline: 0;
        border: 1px solid #ced4da;
      }
      .active_page {
        background-color: #42b983;
      }
    }
    .content {
      width: 100%;
      min-height: 60px;
      background-color: rgba(233, 233, 233, 0.547);
    }
  }
}
</style>
