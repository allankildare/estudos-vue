<template>
  <div class="study-item">
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'vFor',
  data() {
    return {
      items: ['Item 1', 'Item 2', 'Item 3'],
    }
  },
}
</script>