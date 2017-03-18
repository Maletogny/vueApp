<template>
  <div class="users">
  <h1>Users</h1>
  <form v-on:submit="addUser">
    <input type="text" v-model="newUser.name" placeholder="Enter Name">
      <br>
    <input type="text" v-model="newUser.email" placeholder="Enter Email">
      <br>
    <input type="submit" value="Submit">
  </form>
<ul>
  <li v-for="user in users">
    <input type="checkbox" class="toggle" v-model="user.contacted">
    <span :class="{contacted: user.contacted}">
      <b>{{user.name}}: </b> {{user.email}} <button v-on:click="deleteUser(user)" type="button" name="button">Delete</button>
    </span>

  </li>
</ul>

  </div>
</template>

<script>
export default{

name: 'users',

data() {
    return {
    newUser: {},
    users: [
    {
      name: 'John Doe',
      email: 'j.doe@gmail.com',
      contacted: false
    },
    {
      name: 'Mike Ash',
      email: 'm.ash@gmail.com',
      contacted: false
    },
    {
      name: 'Phil Pun',
      email: 'p.pun@gmail.com',
      contacted: false
    },
    ]
    }
  }, //end data
  methods: {

    addUser: function(e){
      this.users.push({
        name: this.newUser.name,
        email: this.newUser.email,
        contacted: false
      })
      e.preventDefault();
    },

    deleteUser: function(user){
      this.users.splice(this.users.indexOf(user), 1);
    }

  }, //end methods


} //end default


</script>

<style scoped>
.contacted{
  text-decoration: line-through;
}

</style>
