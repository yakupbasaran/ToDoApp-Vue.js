<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Todo />
  </div>
</template>

<script>
// @ is an alias to /src
import Todo from "@/components/Todo.vue";

export default {
  name: "Home",
  components: {
    Todo,
  },
};
</script>
