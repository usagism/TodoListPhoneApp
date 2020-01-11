<template>
    <view>
        <view class="inputContainer">
            <text-input class="input" v-model="newTodoText" />
                <touchable-opacity class="add-btn" :on-press="newTodo">
                    <text class="btn-text">Add</text>
                </touchable-opacity>
        </view>

        <view class="todo" v-for="todo in todos" :key="todo.id">
            <touchable-opacity :on-press="() => toggleDone(todo.id)">
                <text class="todo-text done" v-if="todo.done"> {{ todo.title }} </text>
                <text class="todo-text" v-else> {{ todo.title }} </text>
            </touchable-opacity>
            <touchable-opacity class="remove-btn" :on-press="() => removeTodo(todo.id)">
                <text class="remove-btn-text">Remove</text>
            </touchable-opacity>
                
        </view>
    </view>
</template>
<script>
export default {
    data (){
        return {
            newTodoText: '',
            todos: [
                {
                id: 0,
                title: "Studying Programming",
                complete: false
                },
                {
                id: 1,
                title: "Work on Website",
                complete: false
                },
                {
                id: 2,
                title: "Go to the Gym",
                complete: false
                }
            ]
        }
    },
    methods: {
        newTodo() {
            this.todos.push({
                id: this.todos.length + 1,
                title: this.newTodoText,
                complete: false
            })

        },
        toggleDone (id) {
            this.todos = this.todos.map(todo => {
                if (todo.id == id) todo.done = !todo.done
                return todo
            })

        },
        removeTodo (id) {
            this.todos = this.todos.filter(todo => todo.id !==id)

        }
    }
}
</script>

<style scoped>
.inputContainer{
    flex-direction: row;
    justify-content: center;
    align-items: stretch;
}
.input {
    flex: 1;
    height: 35;
    background-color: lightgray;
    font-size: 18px;
    color: black;
}
.add-btn{
    width: 100px;
    height: 35px;
    background-color: green;
    justify-content: center;
    align-items: center;
}
.todo{
flex-direction: row;
justify-content: space-between;
padding: 15px;
}
.todo-text {
    font-size: 18px;
}
.done{
    color: green
}
.remove-btn-text{
    font-size: 18px;
    color: red;
}

</style>