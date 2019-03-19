<template>
  <!-- <v-content> -->
      <v-container>
        <v-layout row>
          <v-flex xs12 sm12>
            <v-card dark>
              <v-divider></v-divider>
              <v-list two-line subheader>
                <v-container>
                  <v-subheader class="headline">{{day}} , {{date}}{{ord}}</v-subheader>
                  <p class="text-xs-right"><b>{{todos.length}}</b> Tasks</p>
                  <v-flex xs12>
                    <v-text-field clearable color="white" v-model="newTodo" id="newTodo" name="newTodo" label="Type your task" @keyup.enter="addTodo">
                    </v-text-field>
                  </v-flex>
                </v-container>
                <v-subheader class="subheading" v-if="todos.length == 0">You have 0 Tasks, add some</v-subheader>
                <v-subheader class="subheading" v-else="todos.length == 1">Your Tasks</v-subheader>
                <div v-for="(todo, i) in todos">
                  <v-list-tile avatar>
                    <v-list-tile-action>
                      <v-checkbox v-if="!todo.done" v-model="todo.done"></v-checkbox>
                    </v-list-tile-action>
                    <v-list-tile-content>
                      <v-list-tile-title :class="{
                  done: todo.done
                  }" class="title">{{todo.title | capitalize}}
                      </v-list-tile-title>
                      <v-list-tile-sub-title>Added on: {{date}}{{ord}} {{day}} {{year}}</v-list-tile-sub-title>
                    </v-list-tile-content>
                    <v-btn icon ripple color="red" @click="removeTodo(i)">
                      <v-icon>close</v-icon>
                    </v-btn>
                  </v-list-tile>
                </div>
              </v-list>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    <!-- </v-content> -->
</template>

<script type="text/javascript">
  export default {
    data () {
      return {
        newTodo: '',
        todo: [],
        todos: [],
        day: this.todoDay(),
        date: new Date().getDate(),
        ord: this.nth(new Date().getDate()),
        year: new Date().getFullYear()
      }
    },
    methods: {
      addTodo () {
        var value = this.newTodo && this.newTodo.trim()
        if (!value) {
          return
        }
        this.todos.push({
          title: this.newTodo,
          done: false
        })
        this.newTodo = ''
      },
      removeTodo (index) {
        this.todos.splice(index, 1)
      },
      todoDay () {
        var d = new Date()
        var days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']
        return days[d.getDay()]
      },
      nth (d) {
        if (d > 3 && d < 21) return 'th'
        switch (d % 10) {
          case 1: return 'st'
          case 2: return 'nd'
          case 3: return 'rd'
          default: return 'th'
        }
      }
    },
    filters: {
      capitalize: function (value) {
        if (!value) return ''
        value = value.toString()
        return value.charAt(0).toUpperCase() + value.slice(1)
      }
    }
  }
</script>