<script>
import { mapGetters } from 'vuex'
import login from './forms/login'

export default {
  name: 'Auth',
  components: {
    login
  },
  computed: {
    ...mapGetters(['isLogged'])
  }
}
</script>

<template>
   <div>
      <header class="page-header row">
         <h2>Confee [Auth]</h2>
      </header>
      <login></login>
   </div>
</template>
