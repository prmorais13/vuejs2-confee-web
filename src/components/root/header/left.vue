<script>
export default {

}
</script>

<template>
   <ul class="nav navbar-nav">
      <router-link :to="{ path: '/dashboard' }" tag="li" exact>
         <a>Home</a>
      </router-link>

      <router-link to="/auth" tag="li">
         <a>Entrar</a>
      </router-link>
   </ul>

</template>
