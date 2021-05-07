<template>
  <div class="todos">
    <br />
    <input class="todotitle" type="text" v-model="todoTitle" /> <br />
    <textarea class="todobody" v-model="todoBody"> </textarea> <br />
    <button class="addtodo" v-on:click="addTodo">Add ToDo</button>
  </div>
</template>

<script>
export default {
  name: "Todo",
  data() {
    return {
      todoTitle: "",
      todoBody: "",
    };
  },
  methods: {
    addTodo: function () { 
      alert(this.todoTitle+"\n"+this.todoBody);
      axios.post(`http://localhost:5000/todo`, { title:this.todoTitle,body:this.todoBody })
            .then(res => {
              console.log(res);
              console.log(res.data);
            })
      this.todoTitle = "";
      this.todoBody = "";
    },
  },
};
</script>


<style scoped>
.todotitle{
  margin:10px;
  width:50%;
  height:25px;
  padding:20px;
  font-size:20px;
  font-weight:bold;
  text-align:center;
  color:rgb(73, 236, 122);
  background-color:#333;
  border:5px solid black;
}
.todobody{
  margin:10px;
  width:50%;
  height:100px;
  padding:20px;
  font-size:18px;
  color:rgb(99, 243, 142);
  background-color:#333;
  border:5px solid black;
}
.addtodo{
  margin:10px;
  width:25%;
  height:50px;
  font-size:20px;
  font-weight:bold;
  color:rgb(0, 0, 0);
  background-color:rgb(73, 236, 122);
  border:5px solid black;
}
</style>
