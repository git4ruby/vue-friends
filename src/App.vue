<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <Navbar />
    <AllFriends :friends="friends" @delete="deleteFriend" />
    <OnlineFriends :friends="friends" />
  </div>
</template>

<script>
import Navbar from './Navbar'
import AllFriends from './AllFriends'
import OnlineFriends from './OnlineFriends'

export default {
  name: 'App',
  components: {
    Navbar,
    AllFriends,
    OnlineFriends
  },
  data(){
    return{
      title: 'My first Vue app, Wooo :-)',
      friends: [
        { name: 'Mohit', online: true },
        { name: 'Munna', online: false },
        { name: 'Chandana', online: true },
        { name: 'CH', online: false }
      ]
    }
  },
  methods: {
    deleteFriend(payload){
      this.friends = this.friends.filter(friend => {
        return friend.name !== payload.name
      })
    }
  }
}
</script>

<style>
h1{
  color: #444;
  font-weight: normal;
  text-align: center;
}
</style>
