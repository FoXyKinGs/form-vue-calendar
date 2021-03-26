<template>
  <div class="d-flex justify-content-center">
    <v-date-picker
    title-position="left"
    popover-visibility='visible'
    v-model='date'
    is-expanded>
    </v-date-picker>
  </div>
</template>

<script>
export default {
  data () {
    return {
      date: new Date()
    }
  }
}
</script>
