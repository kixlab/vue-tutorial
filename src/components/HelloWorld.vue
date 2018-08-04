<template>
  <div class="hello">
    <b-form @submit.prevent="addTodo">
      <b-form-input v-model="input"></b-form-input>
    </b-form>
    <b-list-group>
      <b-list-group-item v-for="(todo, idx) in todos" :key="idx" @click="removeTodo(idx)">{{todo}}</b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
   return {
     todos: [
      'SIG',
      'Dinner',
      'Go Home'
     ],
     input: ''
   }
  },
  methods: {
    addTodo() {
      this.todos.push(this.input);
      this.input = '';
    },
    removeTodo(idx) {
      this.todos.splice(idx, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  margin: 2rem auto 0;
  width: 800px;
}

.list-group {
  margin-top: 1.5rem;
}

.list-group-item {
  text-align: left;
}
</style>
