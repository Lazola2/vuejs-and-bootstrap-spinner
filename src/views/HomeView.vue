<template>
  <Suspense>
    <template #default>
      <ProfileCard/>
    </template>
    <template #fallback>
      <h1>Loading...</h1>
    </template>
  </Suspense>
</template>

<script>
// @ is an alias to /src
import ProfileCard from '@/components/ProfileCard.vue';
export default {
  name: 'HomeView',
  components: {
    ProfileCard
  }
}
</script>
