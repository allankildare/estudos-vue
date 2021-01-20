<template>
  <div>
    <h1>Minhas lista de tarefas</h1>
    <button @click="handlerShowHideList">
        Ver a lista
    </button>
    <br>
    <input type="text" v-focus v-model="currentTask" @keyup.enter="addTask">
    <ul v-if="showList">
        <li v-for="(task, index) in tasks"
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
    data: () => ({
        currentTask: '',
        showList: false,
        tasks: [
            { name: 'Fazer o curso', isDone: false},
            { name: 'Aprender bastante', isDone: false }
        ]
    }),
    methods: {
        handlerShowHideList () {
            this.showList = !this.showList
        },
        addTask () {
            this.tasks.push({
                name: this.currentTask,
                isDone: false
            })
            this.currentTask = ''
        },
        complete (task) {
            this.tasks = this.tasks.map(t => {
                if (t.name == task.name) {
                    return { ...t, isDone: !t.isDone }
                }
                return { ...t }
            })
        },
        remove (task) {
            this.tasks = this.tasks.filter(t => t.name !== task.name)
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