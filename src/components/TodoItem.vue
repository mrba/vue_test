<template>
    <li>
        <span >
            <input class="inList"
                type="checkbox" 
                v-model="todo.completed"
                :indeterminate="indeterminate"
                v-on:change="checkItem"
            >
            <strong>{{todo.title}} </strong>{{index + 1}}
            <span 
                        @click="toggle"
                        v-if="isFolder">
                        [{{ isOpen ? 'v' : '>' }}]
            </span>
            <ul v-show="isOpen" v-if="isFolder">
                <ItemColor v-for="(color, j) in todo.color"
                            v-bind:color="color"
                            v-bind:indexj="j"
                            v-bind:key="j"
                            v-bind:todo="todo"
                            @sendDataToParent="showConsol"

                />
            </ul>
        </span>
                   
    </li>
  
</template>
<script>
    import ItemColor from "@/components/ItemColor"
    export  default {
        props: {
            
            todo: {
                type: Object,
                required: true,
               }, 
            index: Number,
        },
        data: function() {
        return {
            isOpen: false,
            indeterminate: false

            };
        
        },
        computed: {
            isFolder: function() {
            return this.todo.color && this.todo.color.length;
            },
            checkItem(){
                const NewchekAll = this.todo.color.map(chekAll => {
                  return chekAll})

                  for (let i = 0; i < this.todo.color.length; i++){
                      if (this.todo.completed){
                          this.todo.color[i].completed=true
                          this.indeterminate = false
                    
                    console.log( this.indeterminate)

                } else { this.todo.color[i].completed=false
                console.log(  this.indeterminate)
                }}
                
            }

            },
        watch: {
            
            },        
        methods: {
            toggle: function() {
                if (this.isFolder) {this.isOpen = !this.isOpen;}},
            
            showConsol(){
              const NewchekAll = this.todo.color.map(chekAll => {
                  return chekAll})
                  if (NewchekAll.every(e => e.completed === true))
                  {this.indeterminate = false
                  this.todo.completed = true
                  }
                  else if (NewchekAll.every(e => e.completed === false))
                  {this.todo.completed = false
                  this.indeterminate = false 
                  }
                  
                  else {this.indeterminate = true 
                        this.todo.completed = false}
                             
                    }

                    
                 },
                   
                     
                
////////////////////////////////////////////////

// var data = document.querySelectorAll('input.thing'),
//   checkall this.todo.completed = document.getElementById('checkall');

// for (var i = 0; i < data.length; i++) {
//   data[i].onclick = function() {
//     var checkedCount = document.querySelectorAll('input.thing:checked').length;

//     checkall.checked = checkedCount > 0;
//     checkall.indeterminate = checkedCount > 0 && checkedCount < checkboxes.length;
//   }
// }

// checkall.onclick = function() {
//   for (var i = 0; i < checkboxes.length; i++) {
//     checkboxes[i].checked = this.checked;
//   }
// }


//////////////////////////////////////////////////
            components: {
                ItemColor, },
    }
    

</script>
<style scoped>
body {
  padding: 20px;
}
    li {
        border: 1px solid #ccc;
        display: flex;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }

    .inList {
            border: 1px solid red;

    }
   
</style>