<template>
  <div>
    <h1>Minhas lista de tarefas</h1>
    <button @click="handlerShowHideList">
        Ver a lista
    </button>
    <br>
    <input type="text" v-focus v-model="state.currentTask" @keyup.enter="addTask">
    <ul v-if="state.showList">
        <li v-for="(task, index) in state.tasks"
            @dblclick="complete(task)"
            :key="`${task}-${index}`"
            class="task-item"
            :class="{
                'line-through': task.isDone == true
            }">
            {{ task.name }}
            <button @click="remove(task)">
                &times;
            </button>
        </li>
    </ul>
    <p v-else>Lista de tarefas escondidas</p>
  </div>
</template>

<script>
import AppVue from '../../data-binding/App.vue'
const focus = {
    // criando directiva de foco
    inserted: (el) => {
        el.focus()
    }
}

export default {
    // registrando diretiva
    directives:{
        focus
    },
    setup () {
        const state = reactive({
            currentTask: '',
            showList: false,
            tasks: [
                { name: 'Fazer o curso', isDone: false},
                { name: 'Aprender bastante', isDone: false }
            ]
        })

        function handlerShowHideList () {
            state.showList = !state.showList
        }

        function addTask () {
            state.tasks.push({
                name: state.currentTask,
                isDone: false
            })
            state.currentTask = ''
        }

        function complete (task) {
            state.tasks = state.tasks.map(t => {
                if (t.name == task.name) {
                    return { ...t, isDone: !t.isDone }
                }
                return { ...t }
            })
        }

        function remove (task) {
            state.tasks = state.tasks.filter(t => t.name !== task.name)
        }

        return {
            state,
            handlerShowHideList,
            complete,
            remove,
            addTask
        }
    }
}
</script>
<style scoped>
/* com scoped, o css fica com escopo apenas para os componentes */
.line-through {
    text-decoration: line-through;
}
.task-item {
    cursor: pointer;
}
</style>