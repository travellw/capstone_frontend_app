<template>
  <div id="app">
    
    <router-view/>
  </div>
</template>

<style>

</style>


#just in case I change my mind
<div id="nav">
       <router-link to="/login">Login</router-link>
       <router-link to="/">Landing Page</router-link> 
       <router-link to="/dashboard">Dashboard</router-link> 
       <router-link to="/about">About</router-link>
       <router-link to="/signup">Signup</router-link>
    </div>


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}