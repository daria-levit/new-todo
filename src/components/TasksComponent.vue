<template>
    <div class="container">
        <div class="list">
            <div class="task">
                <div class="task-left">
                    <input
                            type="checkbox"
                            class="checkbox"
                            @click="isDone(task.id)"
                    >
                    <div class="text">
                        {{ task.title }}
                    </div>
                </div>
                <v-btn
                        class="task-button-right"
                        small text icon
                        @click="deleteTask(task.id)"
                >
                    <v-icon>mdi-close</v-icon>
                </v-btn>
<!--                <input-->
<!--                        type="button"-->
<!--                        class="task-button-right"-->
<!--                        value="✕"-->
<!--                        @click="deleteTask(task.id)"-->
<!--                >-->
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'TasksComponent',
        props: {
            task: {
                type: Object,
                default: () => ({}),
            },
        },
        methods: {
            isDone(id) {
                this.$emit('isDone', id);
            },
            deleteTask(id) {
                this.$emit('deleteTask', id);
            },
        },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .container {
        height          : 45px;
        display         : flex;
        justify-content : center;
        font-size       : 18px;
    }
    .list {
        display        : flex;
        flex-direction : column;
        width          : 300px;
    }
    .task {
        display : flex;
        align-items: center;
    }
    .task-left {
        display    : flex;
        width      : 100%;
        /*margin-top : 15px;*/
    }
    .checkbox {
        min-width : 20px;
        height    : 20px;
        margin: auto 0;
    }
    .checkbox:checked ~ .text {
        text-decoration : line-through;
    }
    .text {
        margin : 0 0 0 10px;
        color: white;
        font-size: 22px;
    }
    .task-button-right {
        /*margin    : 15px 0 0 10px;*/
        width     : 20px;
        height    : 20px;
        padding   : 0;
        font-size : 16px;
    }
</style>