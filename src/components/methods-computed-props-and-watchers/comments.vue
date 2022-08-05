<template>
  <div class="study-item">
    <ul>
      <li v-for="comment in comments" :key="comment">
        {{ comment }}
      </li>
    </ul>

    <input
      @keyup.enter="addNewComment"
      type="text"
      name="comment"
      placeholder="Digite aqui seu comentário..."
      v-model="newComment"
    />
  </div>
</template>

<script>
export default {
  name: 'comments',
  data() {
    return {
      newComment: '',
      comments: [
        'Este repositório traz conceitos importantes do Vue',
        'Os métodos são coisas incríveis',
      ],
    }
  },
  methods: {
    addNewComment() {
      this.comments.push(this.newComment)
      this.newComment = ''
    },
  },
}
</script>

<style>
</style>