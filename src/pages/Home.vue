<template>
  <div>
    <Form @addNote="addNote"></Form>
    <ListNotes @deleteNote="deleteNote" :notes="notes" />
  </div>
</template>

<script>
import Form from '@/components/notes/Form.vue'
import ListNotes from '@/components/notes/ListNotes.vue'

import notes from '@/seeders/notes.json'

export default {
  components: {
    Form,
    ListNotes
  },
  data() {
    return {
      notes: notes
    }
  },
  methods: {
    addNote(newNote) {
      this.notes.push(newNote)
    },

    deleteNote(index) {
      this.notes.splice(index, 1)
    },
    getNotes() {
      const localNotes = JSON.parse(localStorage.getItem('notes'))
      if (localNotes) {
        this.notes = localNotes
      }
    }
  },
  watch: {
    notes: {
      handler: function (updatedList) {
        localStorage.setItem('notes', JSON.stringify(updatedList))
      },
      // необходимо следить не за самим массивом,
      // а за элементами внутри него
      deep: true
    }
  },
  created() {
    this.getNotes()
  }
}
</script>

<style lang="scss"></style>
