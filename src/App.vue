<template>
  <div id="app">
    <h2>What's up</h2>
    <h1>Welcome to our website {{ user.username }}</h1>
    <my-component v-if="bull"></my-component>


    <div class="">
      Username: <input type="text" v-model="user.username">
      Firstname: <input type="text" v-model="user.firstname">
      Lastname: <input type="text" v-model="user.lastname">
    </div>

    <br>

    <div class="">
      email: <input type="email" v-model="user.email">
      password: <input type="password" v-model="user.password">
    </div>

    <p>
      Display my boolean: {{bull}}
    </p>

    <p>
      <button @click="toggleBull">Show Paragraph</button>
    </p>

    <h3 v-if="bull">Hello, {{user.firstname }} {{user.lastname}}. You are logged in as {{user.username}} with email: {{user.email}}. We're glad to have you.</h3>

  </div>
</template>

<script>
import MyComponent from './components/myComponent.vue';
export default {
  data() {
    return {
      user: {
        username: '',
        firstname: '',
        lastnamme: '',
        email: '',
        password: ''
      },
      bull: true
    };
  },
  methods: {
    toggleBull() {
      this.bull = !this.bull;
    }
  },
  components: {
    MyComponent
  }
};
</script>

<style>
</style>
