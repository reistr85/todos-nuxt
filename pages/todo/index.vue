<template>
  <div class="container container-nuxt">
    <div class="title">
      <h1 class="text-center">Todos</h1>
    </div>

    <div class="container-fluid mt-5">
      <div class="card">
        <div class="card-header">
          Start typing
        </div>
        <div class="card-body min-height">
          <div class="row p-1" v-if="this.$store.state.todos.list.length == 0">
            <div class="col-12">
              <h3 class="text-center">Empty Tasks</h3>
            </div>
          </div>

          <div class="row p-1" v-for="todo in todos" :key="todo.id">
            <div class="col-10">
              <li>{{ todo.text }}</li>
            </div>

            <div class="col-2 text-right">
              <button @click="removeTodo(todo)" class="btn btn-danger btn-sm">
                <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-trash" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                  <path d="M5.5 5.5A.5.5 0 0 1 6 6v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5zm2.5 0a.5.5 0 0 1 .5.5v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5zm3 .5a.5.5 0 0 0-1 0v6a.5.5 0 0 0 1 0V6z"/>
                  <path fill-rule="evenodd" d="M14.5 3a1 1 0 0 1-1 1H13v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V4h-.5a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1H6a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1h3.5a1 1 0 0 1 1 1v1zM4.118 4L4 4.059V13a1 1 0 0 0 1 1h6a1 1 0 0 0 1-1V4.059L11.882 4H4.118zM2.5 3V2h11v1h-11z"/>
                </svg>
              </button>
            </div>
          </div>
        </div>

        <div class="card-footer">
          <input @keyup.enter="addTodo" placeholder="What needs to be done?" class="form-control" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
import NavBarComponent from '@/components/NavBarComponent';

export default {
  name: 'Todo',

  computed: {
    todos() {
      return this.$store.state.todos.list
    }
  },
  methods: {
    addTodo(e) {
      this.$store.commit('todos/add', e.target.value)
      e.target.value = ''
    },
    ...mapMutations({
      toggle: 'todos/toggle'
    }),
    removeTodo(todo) {
      this.$store.commit('todos/remove', todo)
    }
  },
  components: {
    NavBarComponent,
  },
};
</script>

<style lang="scss" scoped>
.min-height {
  min-height: 200px !important;
}
</style>
