<template>
  <div class="note-form__wrapper">
    <form class="note-form" @submit.prevent="addNote">
      <textarea
        required
        v-model="valueNote.title"
        placeholder="Введите новую заметку"
      ></textarea>
      <ListTags :tags="tags" @addTag="addTag"></ListTags>
      <button class="btn btnPrimary" type="submit">Добавить</button>
    </form>
  </div>
</template>

<script>
import ListTags from '@/components/UI/ListTags.vue'
export default {
  components: {
    ListTags
  },
  data() {
    return {
      valueNote: {
        title: '',
        tagsActive: []
      },
      tags: ['дом', 'работа', 'путешествия']
    }
  },
  methods: {
    addNote() {
      this.$emit('addNote', {
        title: this.valueNote.title,
        tag: this.valueNote.tagsActive
      })
      this.valueNote.title = ''
    },
    addTag(tagsActive) {
      console.log(tagsActive)
      this.valueNote.tagsActive = [...tagsActive]
    }
  }
}
</script>

<style lang="scss"></style>
