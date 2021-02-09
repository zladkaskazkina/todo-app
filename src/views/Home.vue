<template>
  <div class="home">
    
    <div class="container">
      <todo-day></todo-day>
    </div>
    <right-controls></right-controls>
  </div>
</template>

<script>
// @ is an alias to /src
import RightControls from '../components/RightControls.vue';
import TodoDay from '../components/TodoDay.vue';

export default {
  name: "Home",
  components: {
    RightControls,
    TodoDay
  }
};
</script>

<style scoped>
.home {
  display: flex;
  justify-content: space-between;
}
.container {
  overflow: hidden;

}
</style>