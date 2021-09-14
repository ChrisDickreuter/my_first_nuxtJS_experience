<template>
  <v-card width="340px" 
          hover 
          class="ma-2"
  >
    <v-img :src="video.thumbnail" />
    <v-card-title>{{ video.name }}</v-card-title>
  </v-card>
</template>

<script>

export default {
    props: ['video'],  
}
</script>

<style scoped lang="scss">
</style>