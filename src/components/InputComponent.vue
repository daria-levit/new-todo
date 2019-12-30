<template>
    <div class="input-task">
        <div class="input">
            <v-text-field
                    height="28"
                    v-model="someTask"
                    @keypress.enter.prevent="addTask"
                    placeholder="add to the list"
                    type="text"
                    name="textview"
                    solo
                    dense
            ></v-text-field>
        </div>
        <div class="button">
            <v-btn
                    normal
                    @click="addTask"
            >
                OK
            </v-btn>
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
        margin   : 30px 5px 30px 5px;
    }
    .input {
        padding: 0;
        width: 250px;
    }
    .button {
        margin : 0 0 0 15px;
    }
</style>