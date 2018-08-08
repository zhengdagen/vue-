<template>
  <div>
    <div>
      <input v-model="inputValue"/> 
      <button @click="handclick">提交</button>
    </div>
    <div>
      <ul>
          <Todo-Item 
              v-for="(item,index) of list"
              :content="item"
              :index="index"
              @delete="handdelete"
          ></Todo-Item>
      </ul>
    </div>

  </div> 
  
</template>

<script>
//引入组件模板
import TodoItem from './components/TodoItem'
export default {
  components:{
    'Todo-Item':TodoItem
  },
  data:function(){
        return {
            inputValue:'',
            list:[]
        }
  },

  methods:{
    handclick(){
        this.list.push(this.inputValue);
        this.inputValue='';
    },
    handdelete(index){
        this.list.splice(index,1);
    }
  }

}
</script>

<style>

</style>
