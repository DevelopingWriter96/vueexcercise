<template>
    <div id="excerciseTable">
        <thead>
            <tr>
                <th>Date</th>
                <th>Name</th>
                <th>Amount</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="newExcercise in excercise" :key="excercise.id">
                <td>{{ newExcercise.date }}</td>
                <td>{{ newExcercise.name }}</td>
                <td>{{ newExcercise.amount }}</td>
            </tr>
        </tbody>
    </div>
</template>

<script>
export default {
    name: 'My Excercise Tracker',
    props: {
        excercise: Array,
    }
}
</script>

<style scoped>

table {
    width: 100%;
}

th {
    margin-right: 2rem;
} 

td {
    margin-right: 2rem;
}

</style>