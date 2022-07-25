<!-- eslint-disable prettier/prettier -->
<template>
  <div class="event-card">
    <span>@ {{ event.time }} on {{ event.date }}</span>
    <h4>{{ event.title }}</h4>
  </div>
</template>

<script>
export default {
  name: "EventCard",
  props: {
    event: Object,
  },
};
</script>

<style scoped>
.event-card {
  padding: 1.2rem;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 1.6rem;
  transition-duration: 500ms;
}

.event-card:hover {
  transform: scale(1.02);
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.2);
}
</style>
