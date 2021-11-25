<template>
  <div>
    <h2>登録</h2>
    <label for="email">Email:</label>
    <input id="email" type="email" v-model="email">
    <br><br>
    <label for="password">パスワード：</label>
    <input id="password" type="password" v-model="password">
    <br><br>
    <button @click="register">送信</button>
  </div>
</template>

<script>
import axios from '../axios-auth';
export default {
  data() {
    return {
      email: "",
      password: ""
    }
  },
  methods: {
    register() {
      axios.post(
        'accounts:signUp?key=AIzaSyDWkE2yR1fbYghiTN8if6Tr4qHKS7uiNzQ',
        {
          email: this.email,
          password: this.password,
          returnSecureToken: true
        }
      ).then(response => {
        console.log(response);
      })
      this.email = "";
      this.password = "";
    }
  }
}
</script>
