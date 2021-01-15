<template>
  <div>
    <h1>Events</h1>
    <EventCard
      v-for="(event, index) in events"
      :key="index"
      :event="event"
    ></EventCard>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios, error }) {
    try {
      const response = await $axios.get('http://localhost:3000/events')
      return {
        events: response.data,
      }
    } catch (e) {
      error({
        statusCode: 503,
        message: 'Unable to fetch this time. Please try again.',
      })
    }
  },
  head() {
    return {
      title: 'Event Listing',
    }
  },
}
</script>
