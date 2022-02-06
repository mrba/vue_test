<template>
             <router-link to="/">Home</router-link>
<div class="forma">
 <div class="list"> 
        
        <Loader v-if="loading" />
        <TodoList
                v-bind:todos="todos"

        />
        <!-- Выше в объекте передаю данные в дочерний элемент -->

    </div>
   <div class="item">
      <ul>
        <li>
        
         </li>
       </ul>
    </div>
</div>
</template>
<script>
    import TodoList from "@/components/TodoList"
    import Loader from "@/components/Loader"
    import Item from "@/components/Item"


    export default {
        name: 'App',
        data(){
            return {
                todos:[
                    {id:1, title: 'list', completed:false, color : [
                        {id: 1,  name: 'Item', inputNum: 10, inputColor: '#fffcb2', completed:false},
                        {id: 2,  name: 'Item', inputNum: 7, inputColor: '#e66456', completed:false},
                        {id: 3,  name: 'Item', inputNum: 5, inputColor: '#17d868',completed:false},
                        {id: 4,  name: 'Item', inputNum: 0, inputColor: '#3c00ff', completed:false},
                        {id: 5,  name: 'Item', inputNum: 10, inputColor: '#fffcb2', completed:false},]},
                    {id:2, title: 'list', completed:false, color : [
                        {id: 6,  name: 'Item', inputNum: 16, inputColor: '#e66456', completed:false},
                        {id: 7,  name: 'Item', inputNum: 5, inputColor: '#17d868',completed:false},
                        {id: 8,  name: 'Item', inputNum: 0, inputColor: '#3c00ff', completed:false},]},
                    {id:3, title: 'list', completed:false, color : [
                        {id: 9,  name: 'Item', inputNum: 10, inputColor: '#fffcb2', completed:false},
                        {id: 10, name: 'Item', inputNum: 16, inputColor: '#e66456', completed:false},
                        {id: 11, name: 'Item', inputNum: 6, inputColor: '#17d868',completed:false},
                        {id: 12, name: 'Item', inputNum: 0, inputColor: '#3c00ff', completed:false},]},
                    {id:4, title: 'list', completed:false, color : [
                        {id: 13, name: 'Item', inputNum: 10, inputColor: '#fffcb2', completed:false},
                        {id: 14, name: 'Item', inputNum: 16, inputColor: '#e66456', completed:false},
                        {id: 15, name: 'Item', inputNum: 4, inputColor: '#17d868',completed:false},
                        {id: 16, name: 'Item', inputNum: 0, inputColor: '#3c00ff', completed:false},]},
                    {id:5, title: 'list', completed:false, color : [
                        {id: 17, name: 'Item', inputNum: 10, inputColor: '#fffcb2', completed:false},
                        {id: 18, name: 'Item', inputNum: 16, inputColor: '#e66456', completed:false},
                        {id: 18, name: 'Item', inputNum: 5, inputColor: '#17d868',completed:false},
                        {id: 20, name: 'Item', inputNum: 0, inputColor: '#3c00ff', completed:false},]}
                ],
                loading: true,

                }
                },
        mounted(){
            this.loading= false
                 },
                //  монтируем состояние в дом
        computed: {

            },
        methods: {
},
        components: {
            TodoList, Loader, Item
        },
}

</script>
<style scoped>
.forma {
  display: flex;
  margin: 5px;
  width: 1024px;
  border: 1px solid black;
  }
  .list {
  margin: 5px;
  width: 550px;
  padding: 5px;
  border: 1px solid black;
  text-align: left;

}
.item {
  margin: 5px;
  width:  550px;
  padding: 5px;
    border: 1px solid black;
      text-align: left;


}
  li {
    margin: 2px;
    list-style: none;
  }
 ul {
    margin: 2px;
    padding: 1px;

  }



</style>
