<template>
  <div class="events">
    <h1>Events for Goods</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue";
import EventServices from "@/services/EventServices";

export default {
  name: "HomeView",
  components: {
    EventCard,
  },
  data() {
    return {
      events: null,
    };
  },
  created() {
    EventServices.getEvents()
      .then((response) => {
        this.events = response.data;
      })
      .catch((error) => {
        console.log("error", error);
      });
  },
};
</script>

<style scoped>
.events {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
