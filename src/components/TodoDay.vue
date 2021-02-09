<template>
  <div class="card todo-day">
    <div class="header">
      <h3 class="day-of-week">{{ weekday }}</h3>
      <h6 class="day">Date</h6>
    </div>
    <div class="todo-list">
      <div class="items" v-if="todoItems">
        <div class="checkbox" v-for="item in todoItems" :key="item.id">
          <input type="checkbox" v-model="item.completed">
          <p class="label" :class="{ completed: item.completed}"> {{ item.title }} </p>
        </div>
      </div>
      <div class="todo-item-input">
        <input class="input" type="text" name="" id="" v-model.trim="newTodo">
        <button @click="addItem">+</button>
      </div>    
    </div>
  </div>
</template>

<script>
export default {
  props: {
    selectedDate: {
      type: Object,
      required: true
    },
    weekday: {
      type: String,
      required: true
    },
  },
  data() {
    return {
      newTodo: '',
      todoItems: [],
    }
  },
  methods: {
    addItem(){
    if(this.newTodo){
      let value = this.newTodo;
      let itemId;
      if(this.todoItems){
        itemId = this.todoItems.length + 1;
      } else {
        itemId = 1;
      }
      this.todoItems.push({
          id: itemId,
          title: value,
          completed: false
       });
      }
      this.newTodo = '';
    }
  },
  computed: {
    selectedMonth() {
      return this.selectedDate.format("MMMM YYYY");
    }
  }
}
</script>
<style scoped>
.header {
  text-align: center;
  padding: 2em 0;
}
.checkbox {
  display: flex;
  height: 2em;
  align-items: center;
}
.card {
  padding: 0.5em;
}
.completed {
  color: #ccc;
  text-decoration: line-through;
}
.label {
  margin: 0 0 0 30px;
  border-bottom: 1px solid #ddd;
}
.todo-item-input {
  margin: 0 0 0 30px;
  padding: 0 30px 0 0;
  border-bottom: 1px solid #ddd;
}
.input  {
  border: 0;
}

</style>