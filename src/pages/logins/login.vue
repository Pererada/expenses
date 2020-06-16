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
        <button class="btn btn-primary w-100">
        <strong>Entrar</strong>
        </button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data: () => {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    doLogin () {
      console.log('fazendo novo app')
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
