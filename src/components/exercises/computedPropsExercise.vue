<template>
  <div>
    <section>
      <h1>Crie um post</h1>
      <form @submit.prevent="addPost">
        <input type="text" placeholder="Título" v-model="newTitle" required />
        <input type="text" placeholder="Nome do autor" v-model="newAuthor" required />
        <select v-model="newLabel">
          <option value="" disabled>Adicione o campo do conhecimento</option>
          <option v-for="(label, index) in labels" :key="index" :value="label">
            {{ label }}
          </option>
        </select>
        <button type="submit">Postar</button>
      </form>
    </section>

    <section>
      <select v-model="selected">
        <option value="" disabled>Filtre pelo campo do conhecimento</option>
        <option v-for="(label, index) in labels" :key="index">
          {{ label }}
        </option>
      </select>
      <span v-if="selected !== ''" @click="clearFilters">Limpar filtro</span>

      <div v-for="(post, index) in filteredByLabel" :key="index">
        <div>
          <h2>{{ post.title }}</h2>
          <p>@{{ post.author }}</p>
        </div>
        <div>{{ post.label }}</div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'computedPropsExercise',
  data() {
    return {
      selected: '',
      newTitle: '',
      newAuthor: '',
      newLabel: '',
      labels: [
        'Matemática',
        'Ciência',
        'Língua Portuguesa',
        'Geografia',
        'Computação',
      ],
      posts: [
        {
          title: 'Operandos',
          author: 'allankildare',
          label: 'Matemática',
        },
        {
          title: 'Geografia política',
          author: 'allankildare',
          label: 'Geografia',
        },
        {
          title: 'Dízima periódica',
          author: 'allankildare',
          label: 'Matemática',
        },
        {
          title: 'Algoritmos',
          author: 'allankildare',
          label: 'Computação',
        },
        {
          title: 'Energias renováveis',
          author: 'allankildare',
          label: 'Ciência',
        },
        {
          title: 'Crase',
          author: 'allankildare',
          label: 'Língua Portuguesa',
        },
        {
          title: 'Paroxítonas, Proparoxítonas e oxítonas',
          author: 'allankildare',
          label: 'Língua Portuguesa',
        },
      ],
    }
  },
  methods: {
    addPost() {
      let addedPost = {
        author: this.newAuthor,
        title: this.newTitle,
        label: this.newLabel
      }
      this.posts.push(addedPost)
      this.newAuthor = ''
      this.newTitle = ''
      this.newLabel = ''
    },
    clearFilters() {
      return this.selected = ''
    }
  },
  computed: {
    filteredByLabel() {
      let filter = new RegExp(this.selected, 'i')
      return this.posts.filter(el => el.label.match(filter))
    }
  }
}
</script>
