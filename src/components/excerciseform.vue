<template id="excercise-form">
    <form @submit.prevent="handleSubmit">
        <label>Excercise Date</label>
            <input v-model="newExcercise.date" type="date" />
        <label>Excercise Name</label>
        <select v-model="newExcercise.name">
            <option>Choose one</option>
            <option value="Pushups">Pushups</option>
            <option value="Situps">Situps</option>
            <option value="Squats">Squats</option>
            <option value="Running">Running</option>
        </select>
        <label>How much did you do?</label>
        <input v-model="newExcercise.amount" type="text" />
        <button @click="addNewExcercise">Add Excercise</button>
    </form>
</template>

<script>
export default {
    name: 'excercise',
    data() {
        return {
            newExcercise: {
                date: "",
                name: "",
                amount: "",
            },
        }
    },
    methods: {
        addNewExcercise() {
            this.$emit('add:newExcercise', this.newExcercise)
        }
    }
}
</script>

<style scoped>
    form {
        margin-bottom: 2rem;
        
    }

    input {
        margin-right: 2rem;
    }

    select {
        margin-right: 2rem;
    }
</style>