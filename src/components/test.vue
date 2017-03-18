<template>
  <div>
    <input type="text" v-model="user.firstName"><br />
    <h1>{{title}}</h1>
    <p v-if="showName"><b>Hi,</b> {{user.firstName}} {{user.lastName}}</p>
    <p v-else="showName">Nobody</p>
    <ul>
        <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet(user.firstName)">Say greeting</button>
    <br />
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
  <hr />
  <label for="">First Name</label>
  <input type="text" v-model="user.firstName"></input>
  <br>
  <label for="">Last Name</label>
  <input type="text" v-model="user.lastName"></input>
  <br>
  <br>
  <p><b>{{fullName}}</b></p>
  <h2>{{msg}}</h2>

  </div>
</template>

<script>
export default{
name: 'test',
props: {
  msg: {
    type: String,
    default: 'Title'
  }
},

data() {
    return {
      title:'Hello world',
      user: {
        firstName: 'John',
        lastName: 'Doe',
        age: 41
      }, //user
      showName: true,
      items:[
        {title:'Item One'},
        {title:'Item Two'},
        {title:'Item three'}
      ]
    }
  },
  methods: {
    greet: function(greeting){
      alert(greeting);
    },
    pressKey: function(e){

      console.log(e.target.value)
    },
    enterHit: function(){
      console.log('you hit enter')
    }
  }, //end methods

  computed: {
    fullName:function(){
      return this.user.firstName + ' ' + this.user.lastName;
    }
  }

} //end default


</script>

<style scoped>


</style>
