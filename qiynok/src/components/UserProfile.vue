<template>
  <div class="user-profile">
    <div class="user-panel">
      <h1 class="user-name">{{ user.name }}</h1>
      <div class="user-follower-count">
          Follower: {{follower}}
       </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserProfile',
  data() {
    return{
      followers:0,
      user: {
        id: 1,
        username: 'ZeuS',
        firstname: 'Salom',
        lastname: 'Alikov',
        email: 'zeus@mail.uz',
        isAdmin:true
      }
    }
  },
watch:{},
computed: {
  fulName(){
    return `${this.user.firstname} ${this.user.lastname}`
  }
},
methods:{
  followUser(){
    this.followers++;
  }
},
mounted(){
  this.follower()
}

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
