<template>
<div>
    <ul>
        <TodoItem
                v-for="(todo, i) in todos"
                v-bind:todo="todo"
                v-bind:key="i"
                v-bind:index="i"

        />
        <!-- итерируем черз фор масив тудус и передаем внтурь дочернего компонента данные -->
    </ul>
    
</div>

</template>
<script>
    import TodoItem from "@/components/TodoItem"

    export default {
        props:['todos'],
        // прописываем в пропсах что передаем и какие свойсва могуть у объекта

        components: {     TodoItem  },
        // объявляем компонент
    }
</script>
<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;

    }
</style>