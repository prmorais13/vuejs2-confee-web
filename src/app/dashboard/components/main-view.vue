<script>
import http from '../../../http'

export default {
  mounted () {
    http.get('http://localhost:3000/usuarios')
      .then(response => response.data)
      .then(data => {
        console.log(data)
      })
  }
}
</script>

<template>
   <header class="page-header row">
      <h2>Confee</h2>
   </header>
</template>
