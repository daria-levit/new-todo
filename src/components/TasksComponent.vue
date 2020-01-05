<template>
    <div class="container d-flex justify-center align-center pa-0">
        <div class="list d-flex flex-column">
            <div class="d-flex align-center">
                <div class="task-left d-flex">
                    <v-checkbox
                            @change="isDone(task.id)"
                            v-model="checkbox"
                            class="checkbox ma-0"
                            color="indigo darken-4"
                    >
                    </v-checkbox>
<!--                    <input-->
<!--                            class="checkbox my-auto"-->
<!--                            type="checkbox"-->
<!--                            @click="isDone(task.id)"-->
<!--                    >-->
                    <div class="headline white--text ml-3"
                         :class="{ 'checkbox-done': task.done }"
                    >
                        {{ task.title }}
                    </div>
                </div>
                <v-btn
                        class="task-button-right pa-0"
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
        data: () => ({
            checkbox: false,
        }),
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
    }
    .list {
        width          : 300px;
    }
    .task-left {
        width      : 100%;
    }
    .checkbox {
        min-width : 20px;
        height    : 20px;
    }
    .checkbox-done{
        text-decoration : line-through;
    }
    .task-button-right {
        width     : 20px;
        height    : 20px;
    }
</style>