<template>
  <div class="user-profile">
    <div class="user-panel">
      <h2 class="user-name">{{ fulName }}</h2>
      <h3 class="user-name"> @{{ user.username}}</h3>
      <div class="user-follower-count">
          Follower: {{followers}}
          <button @click="followUser"> Follow</button>
       </div>
        
     </div>   
      <div>
           <TwootItem class="twoots-panel" v-for="twoot in user.twoots" :key="twoot.id" :username="user.username" :twoot="twoot" />
         </div>   
  </div>
  
</template>

<script>
import TwootItem from "./TwootItem.vue";

export default {
  name: 'UserProfile',
  componenets:{TwootItem},
  data() {
    return{
      followers:0,
      user: {
        id: 1,
        username: 'ZeuS',
        firstname: 'Salom',
        lastname: 'Alikov',
        email: 'zeus@mail.uz',
        isAdmin:true,
        twoots:[
          {id:1, content:'First content there' } ,
          {id:2, content: "Another content wrote down!"}
        ]
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
  this.followUser();
},

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.user-profile{
  display: grid;
  grid-template-columns: 1fr 3fr;
  width: 120%;
  
 
  padding: 50px 5%;

}
.user-panel{
  
  display: flex;
  flex-direction: column;
  margin-right: 50px;
  padding: 20px;
  background-color: #aff;
  border: solid 1px rgb(63, 47, 47);
  border-radius: 5px;

}
h2{
  margin: 5px 0;
}




</style>
