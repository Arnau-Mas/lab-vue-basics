<template>
    <div>
        <div v-for="alumn in alumns" :key="alumn.id">
            <h3>Name: {{alumn.name}}</h3>
            <p>Age: {{alumn.age}}</p>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
        alumns:[
            {
            name:"Arnau",
            age: 26,
            id:1
            },
            {
            name:"Andrew",
            age: 21,
            id:2
            },
            {
            name:"Sara",
            age: 25,
            id:3
            },
            {
            name:"Sophie",
            age: 29,
            id:4
            }
        ]
        }
    }
}
</script>

<style>

</style>