<template>
    <p>Edit the Event</p>
</template>

<script>
export default {
  props: ['event'],
  data: function() {
    return {
        unsavedChanges: true
    }
  },
  beforeRouteLeave() {
    if (this.unsavedChanges) {
        const answer = window.confirm(
            'Do you really want to leave? ...'
        )
        if (!answer) {
            return false
        }
    }
  }
}
</script>