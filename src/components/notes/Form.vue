<template>
  <div class="note-form__wrapper">
    <form class="note-form" @submit.prevent="handleAddNote">
      <textarea
        required
        v-model="defaultNote.title"
        placeholder="Введите новую заметку"
      />
      <ListTags :tags="tags" @onStoreTag="handleAddTag" />
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
      defaultNote: {
        title: '',
        tagsActive: []
      },
      tags: ['дом', 'работа', 'путешествия']
    }
  },
  methods: {
    handleAddNote() {
      this.$emit('onStoreNote', {
        title: this.defaultNote.title,
        tag: this.defaultNote.tagsActive
      })
      this.defaultNote.title = ''
    },
    handleAddTag(tagsActive) {
      this.defaultNote.tagsActive = [...tagsActive]
    }
  }
}
</script>
