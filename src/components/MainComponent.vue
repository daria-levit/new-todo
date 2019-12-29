<template>
    <div class="main">
        <HeaderComponent />
        <InputComponent
                @addTask="addTask"
        />
        <TasksComponent
                v-for="task in sortedList"
                :key="task.id"
                :task="task"
                @isDone="isDone"
                @deleteTask="deleteTask"
        />
    </div>
</template>

<script>
    import HeaderComponent from './HeaderComponent.vue';
    import InputComponent from './InputComponent.vue';
    import TasksComponent from './TasksComponent.vue';
    export default {
        name: 'MainComponent',
        components: {
            HeaderComponent,
            InputComponent,
            TasksComponent,
        },
        data: () => ({
            toDoList: [],
            someTask: '',
        }),
        computed: {
            sortedList() {
                const newList = [...this.toDoList];
                // const newList = this.toDoList.concat();
                return newList.sort((a, b) => {
                    if (!a.done && b.done) return -1;
                    return 1;
                });
            },
        },
        methods: {
            addTask(someTask) {
                if (someTask === '') {
                    return;
                }
                this.toDoList.push({
                    title: someTask,
                    id: new Date().getTime(),
                    done: false,
                });
                this.someTask = '';
            },
            isDone(id) {
                const task = this.toDoList.find((item) => (item.id) === id);
                task.done = !task.done;
            },
            deleteTask(id) {
                this.toDoList = this.toDoList.filter((task) => (task.id) !== id);
            },
        },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>