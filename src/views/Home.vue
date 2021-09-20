<template>
  <div class="home">
    <HomeMobile/>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeMobile from '@/components/HomeMobile.vue'

export default {
  name: 'Home',
  components: {
    HomeMobile
  }
}
</script>
