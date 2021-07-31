<template>
  <div>
    <h1>Entre na sua conta</h1>
    <hr />
    <div>
      <label>Usuário</label>
      <input v-model="login.email" type="text" />
    </div>
    <div>
      <label>Senha</label>
      <input v-model="login.password" type="text" />
    </div>
    <div>
      <!-- <nuxt-link to="/area-membros" class="botao-primario">Entrar</nuxt-link> -->
      <button @click="loginUser()" to="/area-membros" class="botao-primario">
        Entrar
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      login: {
        email: "",
        password: ""
      }
    };
  },
  methods: {
    loginUser() {
      this.$auth
        .loginWith("local", {
          data: this.login
        })
        .then(auth => {
          console.log("sucesso auth", auth);
        })
        .catch(err => {
          console.log("error", err);
        });
    }
  }
};
</script>
