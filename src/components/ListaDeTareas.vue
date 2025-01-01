<template>
    <div>
        <h2>Lista de tareas</h2>
        <!--El v-model es una directiva que nos permite la vinculacion bidireccional de datos con un elemento de formulario y un estado de vue-->
        <!--@keyup.enter es la directiva que nos permite ejecutar una funcion cuando le demos click a enter-->
        <input type="text" v-model="nuevaTarea" @keyup.enter="addTarea" name="" id="">
        <ul>
            <!--La directiva v-for nos permite hacer for each de una lista, es decir agregar los elementos-->
            <!--tarea es el nuevo elemento creado al dar click en enter-->
            <!--index es la posicion en la que se va a asignar cada nuevo elemento-->
            <!--in tareas es en donde se va a mostrar la nueva tarea creada-->
            <!--La directiva :key="index" le asigna un identificador unico a cada elemento agregado-->
            <li v-for="(tarea, index) in tareas" :key="index">
                {{ tarea }}
            </li>
        </ul>
    </div>
</template>

<script setup>
//Objeto reactivo
import { ref } from 'vue';
// el ref se asgina a la contaste tareas que es un arreglo vacio
const tareas = ref([]);
//Otro objeto de ref que va a estar vacio, cuando escribamos algo en el imput se va a agregar
const nuevaTarea = ref([]);
//Funcion que nos permite añadir una nueva tarea a la lista 
const addTarea = () => {
    //.value nos permite tomar el valor de la variable reactiva tareas
    //push se usa cuando se quiere agregar valores aun arreglo
    //nuevaTarea.value reconoce el valor de la tarea agregada
    tareas.value.push(nuevaTarea.value);
    //con esto dejamos vacio el valor de nuevaTarea
    nuevaTarea.value = '';
}
</script>

<style scoped></style>