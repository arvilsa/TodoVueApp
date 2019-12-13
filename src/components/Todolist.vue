<template>
    <div>
    <input type="text" placeholder="Description" v-model="todo.description"/>
    <input type="date" placeholder="Date" v-model="todo.date"/>
    <button v-on:click="add">Add</button>
    <table>
        <tbody>
            <tr v-for="(todo, index) in todos" v-bind:key="index">
                <td>{{todo.description}}</td>
                <td>{{todo.date}}</td>
            </tr>
        </tbody>
    </table>
    </div>
    
    
</template>
<script>

export default {
    name:'Todolist',
    data() {
        return{
            todos:[],
            todo: {
                description:'',
                date: ''
                }
        }

    },
    methods: {
        add: function(){
            this.todos.push(this.todo);
            this.todo= {};
        }
    }    

    
}
</script>

<style>
table {
    margin: auto
}

</style>