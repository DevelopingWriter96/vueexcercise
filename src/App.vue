<script setup>
    import NewExcercise from './components/excerciseform.vue'
    import ExcerciseTable from './components/excercises.vue'
</script>

<template>
<h1>Feel the Burn!</h1>
<NewExcercise @add:newExcercise="addExcercise"/>
<ExcerciseTable :excercise="excercise" />
</template>

<script>
export default {
    name: 'app',
    data() {
        return {
            excercise: [
                {
                    id: 1,
                    date: '2023-03-08',
                    name: "Pushups",
                    amount: "100 reps",
                },
                {
                    id: 2,
                    date: '2023-03-08',
                    name: "Situps",
                    amount: "100 reps",
                },
                {
                    id: 3,
                    date: '2023-03-08',
                    name: "Squats",
                    amount: "100 reps",
                },
                {
                    id: 4,
                    date: '2023-03-08',
                    name: 'Running',
                    amount: "100 km",
                },
            ]
        }
    },
    methods: {
        addExcercise(newExcercise) {
            console.log('working')
            const lastId = 
                this.excercise.length > 0
                ? this.excercise[this.excercise.length].id
                : 0
            const id = lastId + 1

            const newExcercise = {
                ...newExcercise,
                id
            } 

            this.excercise = [...this.excercise, newExcercise]
        }
    }
}
</script>