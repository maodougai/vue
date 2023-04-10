<template>
  <div id="app">
    <div class="todo-container">
			<div class="todo-wrap">
				<MyHeader :addTodo="addTodo"></MyHeader>
				<List :todoList="todoList" :checkTodo="checkTodo" :deleteTodo="deleteTodo"></List>
				<MyFooter :todoList="todoList" :checkAllTodo="checkAllTodo" :clearAllTodo="clearAllTodo"></MyFooter>
			</div>
		</div>
  </div>
</template>

<script>
import MyHeader from '@/components/MyHeader'
import List from '@/components/List'
import MyFooter from '@/components/MyFooter'

export default {
  name: 'App',
  components: {
    MyHeader,
    List,
    MyFooter
  },
  data(){
    return{
      todoList:[
        {id:'0001',title:'吃饭',completed:false},
        {id:'0002',title:'睡觉',completed:true},
        {id:'0003',title:'玩耍',completed:true},
      ]
    }
  },
  methods:{
    addTodo(todo){
      this.todoList.unshift(todo);
    }
  }
}
</script>

<style>
/*base*/
body {
		background: #fff;
	}
	.btn {
		display: inline-block;
		padding: 4px 12px;
		margin-bottom: 0;
		font-size: 14px;
		line-height: 20px;
		text-align: center;
		vertical-align: middle;
		cursor: pointer;
		box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
		border-radius: 4px;
	}
	.btn-danger {
		color: #fff;
		background-color: #da4f49;
		border: 1px solid #bd362f;
	}
	.btn-danger:hover {
		color: #fff;
		background-color: #bd362f;
	}
	.btn:focus {
		outline: none;
	}
	.todo-container {
		width: 600px;
		margin: 0 auto;
	}
	.todo-container .todo-wrap {
		padding: 10px;
		border: 1px solid #ddd;
		border-radius: 5px;
	}
</style>
