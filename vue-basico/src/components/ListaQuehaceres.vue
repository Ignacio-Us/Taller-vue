<template>
    <div>
        <h1>{{ title }}</h1>
        <input v-model="title" placeholder="Ingrese el nombre de la lista">
        <br><br>
        <h3>Ingrese una nueva tarea</h3>
        <input v-model="task" placeholder="Ingrese una nueva tarea" />
        <button v-on:click="addTask">+</button>

        <ul>
            <li v-for="t in lista" :key="t">{{ t }} <button v-on:click="removeTask">X</button></li>
            
        </ul>
    </div>
</template>



<script>
export default {
    name: 'ListaQuehaceres',
    data() {
        return {
            title: '',
            task: '',
            lista: []
        }
    },
    methods: {
        addTask() {
            this.lista.push(this.task);
        },
        removeTask() {
            delete this.lista[this.lista.indexOf(this.task)];
            this.lista.pop();
        }
    }
}
</script>