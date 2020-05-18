<template>
<div class="login">
    <!-- Check that the SDK client is not currently loading before accessing is methods -->
    <div class="nav" v-if="!$auth.loading">
      <!-- show login when not authenticated -->
      <button class="button-login" v-if="!$auth.isAuthenticated" @click="login">Login</button>
      <!-- show logout when authenticated -->
      <button class v-if="$auth.isAuthenticated" @click="logout">Log out</button>
      <button class="button-about">About</button>
      <button class="button-documentation">Documentation</button>
      <button class="button-support">Support</button>
    </div>
    <img class="logo" alt="Vue logo" src="../assets/element.png" />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Major+Mono+Display&display=swap');

.nav {
  text-align: center;
}

.logo {
  width: 600px;
  height: 600px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}


.button-login {
  background-color: pink; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 30px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-logout {
  background-color: pink; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 30px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-about {
  background-color: blue; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-documentation {
  background-color: green; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-support {
  background-color: yellow; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

</style>


  <script>
// .. imports removed for brevity

import HelloWorld from "../components/HelloWorld"

export default {
  name: "login",
  components: {
    HelloWorld
  },
  methods: {
    // Log the user in
    login() {
      this.$auth.loginWithRedirect();
    },
    // Log the user out
    logout() {
      this.$auth.logout({
        returnTo: window.location.origin
      });
    }
  }
};
</script>