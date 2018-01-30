<script>
import { mapGetters } from 'vuex'

export default {
  data () {
    return {
      isOpenDropdown: false
    }
  },
  computed: {
    ...mapGetters(['isLogged', 'currentUser'])
  },
  methods: {
    toggleDropdow () {
      this.isOpenDropdown = !this.isOpenDropdown
    }
  }
}
</script>

<template>
  <ul class="nav navbar-nav navbar-right">
    <router-link to="/auth" tag="li" v-if="!isLogged"><a>Entrar</a></router-link>
    <li class="dropdown" :class="{ open: isOpenDropdown }" v-if="isLogged">
      <a href="javascript:;" @click="toggleDropdow" class="dropdown-toggle">{{ currentUser.name }}<span class="caret"></span></a>
      <ul class="dropdown-menu">
        <li><a href="javascript:;">Ação</a></li>
        <li><a href="javascript:;">Outra Ação</a></li>
        <li><a href="javascript:;">Diversos</a></li>
        <li role="separator" class="divider"></li>
        <li><a href="javascript:;">Link Separador</a></li>
      </ul>
    </li>
  </ul>
</template>
