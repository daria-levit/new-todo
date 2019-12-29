<template>
    <div class="input-task">
        <form name="form">
            <input
                    v-model="someTask"
                    type="text"
                    name="textview"
                    placeholder="add to the list"
                    class="input"
                    @keypress.enter.prevent="addTask"
            >
        </form>
        <div class="button">
            <input
                    type="button"
                    value="OK"
                    @click="addTask"
            >
        </div>
    </div>
</template>

<script>
    export default {
        name: 'InputComponent',
        data: () => ({
            someTask: '',
        }),
        methods: {
            addTask() {
                this.$emit('addTask', this.someTask);
                this.someTask = '';
            },
        },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .input-task {
        display         : flex;
        justify-content : center;
        margin-bottom   : 20px;
    }
    .input {
        width : 250px;
    }
    .button {
        margin : 0 0 0 15px;
    }
</style>