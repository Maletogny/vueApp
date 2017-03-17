<template>
  <div>
    <h1>{{title}}</h1>
    <p><b>Hi,</b> {{user.firstName}} {{user.lastName}}</p>
    <p v-text = "user.age"> </p>
  </div>
</template>

<script>
export default{
name: 'test',
data() {
    return {
      title:'Hello world',
      user: {
        firstName: 'John',
        lastName: 'Doe',
        age: 41
      }
    }
  }
}


</script>

<style scoped>


</style>
