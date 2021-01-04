<template>
  <div id="app">
    {{fullName}}
    <span>Followers: {{followers}}</span>
    <button v-on:click="followUser">Follow</button>
  </div>
</template>

<script>

export default {
  name:'App',
  data(){
    return {
      followers: 0,
      user: {
        id: 1,
        userName: 'Barnicle',
        firstName: 'Eugene',
        lastName: 'Galimov',
        email: 'egalimov95@gmail.com',
        isAdmin: true
      }
    }
  },
  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if(oldFollowerCount < newFollowerCount) {
        console.log(`${this.user.userName} gain follower!`)
      }
    }
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`
    }
  },
  methods: {
    followUser() {
      this.followers++;
    }
  },
  mounted() {
    // this.followUser()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  flex-flow: column;
}
</style>
