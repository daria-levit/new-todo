<template>
    <div class="input d-flex justify-center my-7 mx-1">
            <v-text-field
                    class="pa-0"
                    v-model="someTask"
                    @keypress.enter.prevent="addTask"
                    placeholder="add to the list"
                    type="text"
                    name="textview"
                    solo
                    dense
            ></v-text-field>

            <v-btn
                    class="ml-4"
                    normal
                    @click="addTask"
            >
                OK
            </v-btn>
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
.input{
    max-height: 36px;
}
</style>