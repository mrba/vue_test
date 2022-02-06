<template>
<ul>
    <li  >
        <span   >
            <input 
            type="checkbox" 
            id="indexj+1"
            :class="color.name"  
            @change="sendDataToParent" 
            v-model="color.completed"
                 >
                  
             {{color.name}} <strong  >{{indexj+1}}</strong>
            <input class="in" type="number"  min="1" step="1" v-model="color.inputNum">
            <input class="ic" type="color" v-model="color.inputColor">
        </span>
        <span v-if="color.completed">
              <button class="item"
            v-for="colorBox in color.inputNum"
            v-bind:key="colorBox"
            v-bind:id="colorBox"
            :style="{background: color.inputColor}" style="border: 1px solid black; width: 15px; height: 15px"
            v-on:click="color.inputNum--"
          ></button>
        </span>
    
   </li>
</ul>
</template>
<script>
    export  default {
        data() {
            return {
                counter: 0,
            }
        },
        props: {
            color: {
                type: Object,
                required: true,
            },
            todo: {
                type: Object,
                required: true,
            },
            indexj: Number,
        },
        computed:{
            checkAll(){
                if (color.completed){
                   let a=1
                }
            }
        },
           
        methods: { 
            removeTodo() {
                this.colorBox = this.colorBox.remove(id-1)},
            sendDataToParent (){
               // this.todo.completed = !this.todo.completed
                
                this.$emit('sendDataToParent', this.color.completed)

            },

            
            toglle(){
                 if (!this.color.completed && this.color.completed.length) {
                    return (this.todo.completed = indeterminate = true)
                }}},
           
            // },
            // filter1: function() {
            //     if (this.todo.color.completed && this.todo.color.completed.length) {
            //         return (this.todo.completed =  true)
            //     }
            // },
        }
    
</script>
<style scoped>
    li {
        border: 1px solid #ccc;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;

    ;
    }
    .rm {
        background: red;
        color:  #fff;
        border-radius: 50%;
        font-weight: bold;
    }
    .ic {
        border: none;
        width: 25px;
    }
    .in {
        font-size: medium;
        margin-left: 10rem;
        width: 35px;
        border: none;
    }
    
.item {
 border: 2px solid black;
padding-left: 3px;
margin-left: 2px;
height: 10px;
}

</style>