<template>
  <div>
      <h3>AddTodos </h3>
      <div class="add">
          <form @submit="onSubmit">
              <input type="text" v-model="title" placeholder="Add Todo...">
              <input type="submit" value="Submit">
          </form>
      </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: 'AddTodos',
  data () {
    return {
      title: ''
    }
  },
  methods: {
    ...mapActions(['addTodos']),
    onSubmit (e) {
      e.preventDefault()
      this.addTodos(this.title)
    }
  }
}
</script>

<style scoped>
form{
    display: flex;
}
input[type="text"] {
    flex: 10;
    padding: 10px;
    border: 1px solid #41b883;
    outline: 0;
}

input[type="submit"] {
    flex: 2;
    background: #41b883;
    border: 1px solid #41b883;
    cursor: pointer;
}
</style>
