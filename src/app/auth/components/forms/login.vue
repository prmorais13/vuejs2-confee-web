<script>
import { mapActions } from 'vuex'
import { isEmpty } from 'lodash'

export default {
  name: 'Login',
  data () {
    return {
      user: {
        email: '',
        password: ''
      }
    }
  },
  computed: {
    isValid () {
      const user = this.user
      return !isEmpty(user.email) && !isEmpty(user.password)
    }
  },
  methods: {
    ...mapActions(['attemptLogin']),
    doLogin () {
      const user = this.user
      this.attemptLogin({ ...user })
        .then(() => {
          this.$router.push('/')
        })
    }
  }
}
</script>

<template>
<div class="row">
	<div class="col-md-6">
		<div class="form-group">
			<label>Email</label>
			<input type="email" v-model="user.email" class="form-control">
		</div>

		<div class="form-group">
			<label>Senha</label>
			<input type="password" v-model="user.password" class="form-control">
		</div>
		<button type="submit" @click="doLogin" :disabled="!isValid" class="btn btn-default">Submit</button>
	</div>
</div>
  
</template>

