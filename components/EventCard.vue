<template>
  <nuxt-link :to="'/event/' + event.id">
    <div class="card">
      <span> {{ event.time }} on {{ event.date }} </span>
      <h4>{{ event.title }}</h4>
      <span>{{ event.attendees.length }} attending</span>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    // eslint-disable-next-line
    event: Object,
  },
}
</script>

<style>
.card {
  border: 1px solid black;
  height: 200px;
  padding: 20px;
  margin-bottom: 24px;
  cursor: pointer;
}
a:link {
  text-decoration: none;
}
h4 {
  color: black;
}
span {
  color: gray;
}
</style>
