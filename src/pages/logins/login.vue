<template>
   <form @submit.prevent="doLogin()" class="form-login">
    <div class="card">
      <div class="card-header text-center">
        <img src="../../assets/logo-60x60px.png" class="img-fluid" alt="Imagem responsiva">
     <h1 class="mb-2">Avic Food</h1>
      </div>
      <div class="card-body">
        <div class="form-group">
          <input
          required
          type="email"
          v-model="email"
          class="form-control"
          placeholder="E-mail"
          >
        </div>
        <div class="form-group">
          <input
          required
          type="password"
          v-model="password"
          class="form-control"
          placeholder="Senha"
          >
        </div>
        <button class="btn btn-primary w-100" :disabled="loading">
          <template v-if="loading">
            Entrando ...
            <i class="fa fa-spinner fa-spin"></i>
          </template>
          <template>
            Entrar
            <i class="fa fa-sign-in-alt"></i>
          </template>
        </button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  nome: 'login',
  data: () => {
    return {
      loading: false,
      email: 'avic.telecom@gmail.com',
      password: '123123'
    }
  },
  methods: {
    async doLogin () {
      this.loading = true
      const { email, password } = this
      try {
        const res = await this.$firebase.auth().signInWithEmailAndPassword(email, password)

        window.uid = res.user.uid

        this.$router.push({ name: 'home' })
      } catch (err) {
        console.log(err)
      }
      this.loading = false
    }
  }
}
</script>
<style lang="scss" scoped>

.form-login {
height: 100vh;
display: flex;
align-items: center;
justify-content: center;
h1 {
  font-size: 30px;
}
}
.card {
  width: 50%;
  color: var(--dark);
}
.btn {
  font-size: 20px;
  align-items: center;
  justify-content: center;
}

</style>>
