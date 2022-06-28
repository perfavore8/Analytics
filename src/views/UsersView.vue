<template>
  <EditUser v-if="true"></EditUser>
  <div class="wrapper_users" :class="{ blur: true }">
    <div class="container">
      <div class="header">
        <label>Пользователи</label>
      </div>
      <div class="content">
        <div class="list">
          <div class="item" v-for="(user, idx) in users" :key="user.id">
            <button class="modal_button">1</button>
            <div class="icon">{{ shortNames[idx] }}</div>
            <div class="info">
              <label>{{ user.name }}</label>
              <small>{{ user.mail }}</small>
            </div>
          </div>
        </div>
      </div>
      <div class="footer">
        <label>Пригласить</label>
        <div class="out">
          <div class="label_input">
            <label>Электронная почта пользователя</label>
            <input class="input" type="mail" />
          </div>
          <button>Отправить</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import EditUser from "@/components/UsersComponents/EditUser.vue";
export default {
  components: { EditUser },
  name: "UsersView",
  data() {
    return {
      users: [
        {
          id: 1,
          name: "Юрий Попов",
          mail: "mail@exemple.com",
          data: {},
        },
        {
          id: 2,
          name: "Аркадий Вжухов",
          mail: "mail2@exemple.com",
          data: {},
        },
        {
          id: 3,
          name: "Генадий Горин",
          mail: "post@exemple.com",
          data: {},
        },
      ],
    };
  },
  computed: {
    shortNames() {
      let names = [];
      this.users.forEach((item) => {
        const name = item.name.split(" ");
        let lat = [];
        name.forEach((n) => {
          const letters = n.split("");
          lat.push(letters[0]);
        });
        names.push(lat.join(""));
      });
      return names;
    },
  },
};
</script>

<style lang="scss" scoped>
.wrapper_users {
  width: 100%;
  .container {
    display: flex;
    flex-direction: column;
    align-items: start;
    margin: 20px auto;
    background-color: rgba(233, 233, 233, 0.547);
    width: 90%;
    .header {
      width: 95%;
      margin: 20px auto;
      text-align: left;
    }
    .content {
      width: 90%;
      margin: 0 auto 15px;
      min-height: 60px;
      .list {
        display: flex;
        flex-direction: column;
        gap: 10px;
        align-items: start;
        .item {
          display: flex;
          flex-direction: row;
          align-items: center;
          gap: 10px;
          .modal_button {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid #ced4da;
          }
          .icon {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border: none;
            border-radius: 50%;
            background-color: #86b6fe8f;
          }
          .info {
            display: flex;
            flex-direction: column;
            align-items: start;
            gap: 5px;
          }
        }
      }
    }
    .footer {
      width: 95%;
      display: flex;
      flex-direction: column;
      margin: 10px auto;
      gap: 10px;

      label {
        display: flex;
        justify-content: start;
      }
      .out {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: end;
        gap: 10px;

        button {
          width: 90px;
          height: 34px;
          padding: 6px 12px;
          background-color: white;
          border: 1px solid #ced4da;
          border-radius: 4px;
        }
      }
      .label_input {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 5px;
        align-items: start;
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
      }
    }
  }
}
.blur {
  filter: blur(5px);
}
</style>
