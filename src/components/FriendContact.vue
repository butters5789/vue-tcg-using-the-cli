<template>
  <li>
    <h2>{{ friend.name }}</h2>

    <button @click="toggleDetails">{{ detailsButtonText }}</button>

    <ul v-if="showDetails">
      <li><strong>Phone:</strong> {{ friend.phone }}</li>
      <li><strong>Email:</strong> {{ friend.email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'friend-contact',
  data() {
    return {
      friend: {
        id: '1',
        name: 'Brad Butterfield',
        email: 'brad.butterfield@aol.com',
        phone: '123-456-7890',
      },
      showDetails: false,
    };
  },
  computed: {
    detailsButtonText() {
      if (this.showDetails) {
        return 'Hide Details';
      }

      return 'Show Details';
    },
  },
  methods: {
    toggleDetails() {
      this.showDetails = !this.showDetails;
    },
  },
};
</script>

<style></style>
