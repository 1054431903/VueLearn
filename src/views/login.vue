<template>
  <div>
    <form v-if="!isReg">
      <table>
        <thead></thead>
        <tbody>
          <tr>
            <td>userName:</td>
            <td>
              <input type="text" v-model="userName">
            </td>
          </tr>
          <tr>
            <td>passWord:</td>
            <td>
              <input type="password" v-model="passWord">
            </td>
          </tr>
        </tbody>
        <tfoot>
          <td>
            <button type="button" @click="sub()">Login</button>
          </td>
          <td>
            <button type="button" @click="reg()">regist</button>
          </td>
        </tfoot>
      </table>
    </form>
    <form v-else>
      <table>
        <thead></thead>
        <tbody>
          <tr>
            <td>userName:</td>
            <td>
              <input type="text" v-model="userName">
            </td>
          </tr>
          <tr>
            <td>passWord:</td>
            <td>
              <input type="password" v-model="passWord">
            </td>
          </tr>
          <tr>
            <td>rePassWord:</td>
            <td>
              <input type="password" v-model="repeat">
            </td>
          </tr>
        </tbody>
        <tfoot>
          <td>
            <button type="button" @click="addUser()">确认</button>
          </td>
          <td>
            <button type="button" @click="cancel()">取消</button>
          </td>
        </tfoot>
      </table>
    </form>
  </div>
</template>
<script>
export default {
  name: "login",
  data() {
    return {
      isReg: false,
      userName: "",
      passWord: "",
      repeat: ""
    };
  },
  methods: {
    sub() {
      if (localStorage.getItem(this.userName) === this.passWord) {
        this.$router.push("/home/list");
      } else {
        alert("username or password error");
      }
    },
    reg() {
      this.isReg = true;
    },
    addUser() {
      if (this.passWord === this.repeat) {
        if (localStorage.getItem(this.userName) != null) {
          alert("user is exist");
          return;
        }
        localStorage.setItem(this.userName, this.passWord);
        this.isReg = false;
      } else {
        alert("password not equal");
      }
    },
    cancel() {
      this.isReg = false;
    }
  }
};
</script>
<style scoped>
</style>
