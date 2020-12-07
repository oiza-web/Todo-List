<template>
  <div>
    <h3>Add Todo</h3>
    <div class="add">
      <form @submit="onSubmit" >
        <input type="text" v-model="title" placeholder="...Add Todo">
        <input type="submit" value="Submit">
      </form>
      
    </div>
  </div>
</template>

<script>
import {mapActions} from 'vuex';
export default {
  data(){
    return{
      title: ''
    }
  },
    name: 'AddTodo',
    methods:{
      ...mapActions(['addTodo']),
      onSubmit(e){
        e.preventDefault();
        this.addTodo(this.title);
      },

    }

}
</script>

<style>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid palevioletred;
  outline: 0;
}
input[type="submit"] {
  flex: 2;
  background: palevioletred;
  color: #fff;
  border: 1px pink solid;
  cursor: pointer;
}
</style>