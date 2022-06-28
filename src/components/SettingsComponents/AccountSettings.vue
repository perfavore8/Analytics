<template>
  <div class="wrapperac">
    <div class="header"><label>Основные данные</label></div>
    <div class="content">
      <div class="label_input">
        <label class="label">ФИО</label>
        <input class="input" type="text" />
      </div>
      <div class="label_input">
        <label class="label">Номер телефона</label>
        <input class="input" type="tel" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" />
      </div>
      <div class="label_input">
        <label class="label">Электронная почта</label>
        <input class="input" type="text" />
      </div>
      <div class="label_input check">
        <input type="checkbox" v-model="showVIP" />
        <label>Юридическое лицо</label>
      </div>
      <div class="legal" v-if="showVIP">
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
        <div class="label_input">
          <label class="label">ФИО</label>
          <input class="input" type="text" />
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Изменить пароль</p>
      <div class="btns">
        <button v-if="showVIP">Сформировать договор</button>
        <button>Сохранить</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AccountSettings",
  data() {
    return {
      showVIP: true,
    };
  },
};
</script>

<style lang="scss" scoped>
.wrapperac {
  width: 95%;
  margin: 0 auto;
  .header {
    display: flex;
    justify-content: start;
    margin: 10px 0 10px;
  }
  .content {
    display: flex;
    align-items: start;
    flex-direction: row;
    gap: 20px;
    flex-wrap: wrap;
    .label_input {
      width: calc((100% - 20px) / 2);
      display: flex;
      flex-direction: column;
      gap: 5px;
      align-items: start;
      margin: 10px 0;
    }
    .legal {
      width: calc(50% - 10px);
      .label_input {
        width: 100%;
      }
    }
    .input {
      width: calc(100% - 24px);
      height: 20px;
      padding: 6px 12px;
      background-color: white;
      border: 1px solid #ced4da;
      appearance: none;
      border-radius: 4px;
      transition: border-color 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
    }
    .input:focus {
      color: #212529;
      background-color: white;
      border-color: #86b7fe;
      outline: 0;
      box-shadow: 0 0 0 4px rgb(13 110 253 / 25%);
    }
    .check {
      height: 48px;
      flex-direction: row;
      align-items: end;
    }
  }
  .footer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: end;
    padding: 10px;
    margin-top: 20px;
    .btns {
      display: flex;
      flex-direction: row;
      gap: 5px;
    }
    button {
      height: 20px;
    }
    p {
      margin: 0;
    }
  }
}
</style>
