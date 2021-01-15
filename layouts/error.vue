<template>
  <div>
    <p v-if="statusCode === 404">
      Page not found
      <nuxt-link to="/">Home page</nuxt-link>
    </p>
    <p v-else>
      {{ message }}
    </p>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  computed: {
    statusCode() {
      return (this.error && this.error.statusCode) || 500
    },
    message() {
      return this.error.message
    },
  },
  head() {
    return {
      title: this.message,
    }
  },
}
</script>
