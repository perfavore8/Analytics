<template>
  <div class="wrapper_edit_user">
    <div class="container">
      <div class="header">
        <label>Управление доступами к проектам</label>
      </div>
      <div class="content">
        <div class="row">
          <div class="row_head">
            <label>Кондитерская</label>
            <label>Перейти к проекту</label>
          </div>
          <div class="row_content">
            <SelectorVue
              :options_props="options_1"
              @select="option_select_1"
              :selected_option="selected_option_1"
            />
            <MultiSelector
              :options_props="options_3"
              @select="option_select_multi"
              :selected_options="selected_options_3"
            />
          </div>
        </div>
        <div class="row">
          <div class="row_head">
            <label>Ферма</label>
            <label>Перейти к проекту</label>
          </div>
          <div class="row_content">
            <SelectorVue
              :options_props="options_1"
              @select="option_select_1"
              :selected_option="selected_option_1"
            />
            <MultiSelector
              :options_props="options_3"
              @select="option_select_multi"
              :selected_options="selected_options_3"
            />
          </div>
        </div>
        <div class="row">
          <div class="row_head">
            <label>Завод</label>
            <label>Перейти к проекту</label>
          </div>
          <div class="row_content">
            <SelectorVue
              :options_props="options_1"
              @select="option_select_1"
              :selected_option="selected_option_1"
            />
            <MultiSelector
              :options_props="options_3"
              @select="option_select_multi"
              :selected_options="selected_options_3"
            />
          </div>
        </div>
      </div>
      <div class="footer">
        <button>Отмена</button>
        <button>Готово</button>
      </div>
    </div>
  </div>
</template>

<script>
import SelectorVue from "@/components/AppComponents/SelectorVue.vue";
import MultiSelector from "@/components/AppComponents/MultiSelector.vue";
export default {
  name: "EditUser",
  components: {
    SelectorVue,
    MultiSelector,
  },
  data() {
    return {
      options_1: [
        { name: "Товар", value: 1 },
        { name: "Услуга", value: 2 },
      ],
      selected_option_1: { name: "Товар", value: 1 },
      options_2: [
        { name: "Не выбрано", value: 1 },
        { name: "шт", value: 2 },
        { name: "л (литры)", value: 3 },
        { name: "м3 (кубические метры)", value: 4 },
        { name: "кг (килограммы)", value: 5 },
        { name: "т (тонны)", value: 6 },
        { name: "комплект", value: 7 },
        { name: "услуга", value: 8 },
      ],
      selected_option_2: { name: "Не выбрано", value: 1 },
      options_3: [
        { name: "Не выбрано", value: 1 },
        { name: "шт", value: 2 },
        { name: "л (литры)", value: 3 },
        { name: "м3 (кубические метры)", value: 4 },
        { name: "кг (килограммы)", value: 5 },
        { name: "т (тонны)", value: 6 },
        { name: "комплект", value: 7 },
        { name: "услуга", value: 8 },
      ],
      selected_options_3: [true],
    };
  },
};
</script>

<style lang="scss" scoped>
.wrapper_edit_user {
  position: absolute;
  top: 20%;
  left: calc(50% - 400px);
  background-color: #e9e9e9;
  max-width: 800px;
  padding: 50px;
  border-radius: 10px;
  z-index: 999;
  .container {
    margin: 0;
    .header {
      text-align: left;
      margin-bottom: 15px;
    }
    .content {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      gap: 5px;
      margin-bottom: 20px;
      .row {
        width: 230px;
        display: flex;
        flex-direction: column;
        gap: 15px;
        align-items: center;
        border: 1px solid #ced4da;
        border-radius: 8px;
        background-color: #ffffff;
        padding: 15px;
        .row_head {
          width: 100%;
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          height: 40px;
        }
        .row_content {
          display: flex;
          flex-direction: column;
          gap: 15px;
        }
      }
    }
    .footer {
      display: flex;
      flex-direction: row;
      gap: 10px;
      justify-content: end;
    }
  }
}
</style>
