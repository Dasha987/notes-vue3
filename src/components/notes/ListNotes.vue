<template>
  <div class="notes-list">
    <div class="note-item" v-for="(note, index) in notes" :key="index">
      <div class="note-header">
        <p>{{ note.title }}</p>
        <button class="note-btn" @click="$emit('deleteNote', index)">
          &#10005;
        </button>
      </div>
      <div v-if="note.tag != ''" class="note-footer">
        <ListTags isPreview :tags="note.tag"></ListTags>
      </div>
    </div>
  </div>
</template>

<script>
import ListTags from '@/components/UI/ListTags.vue'
export default {
  components: {
    ListTags
  },
  props: {
    notes: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="scss"></style>
