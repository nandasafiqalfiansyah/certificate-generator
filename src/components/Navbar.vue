<template>
  <!-- App Bar -->
  <v-app-bar flat class="mb-4">
    <v-container class="mx-auto d-flex align-center justify-between">
   <v-avatar size="40">
        <v-img src="https://github.githubassets.com/assets/galaxy-brain-default-847262c21056.png" />
      </v-avatar>
      <div class="d-flex align-center">
        <v-btn
          v-for="link in links"
          :key="link"
          :text="link"
          class="me-4"
        ></v-btn>
      </div>

      <v-spacer></v-spacer>
      <!-- Search Field -->
      <v-responsive max-width="160">
        <v-text-field
          density="compact"
          label="Search"
          rounded="lg"
          variant="solo-filled"
          flat
          hide-details
          single-line
        ></v-text-field>
      </v-responsive>
    </v-container>
  </v-app-bar>
</template>

<script setup lang="ts">
const links = [
  'Certificate Generate app',
];
</script>
