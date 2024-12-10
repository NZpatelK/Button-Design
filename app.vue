<template>
  <div>
    <!-- Main Page Content -->
    <main>
      <nuxt-page />
    </main>

    <PaginatedNavbar />
  </div>
</template>

<script setup>
import PaginatedNavbar from '~/components/NavBar.vue';
</script>
