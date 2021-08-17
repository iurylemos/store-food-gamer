<template>
  <div class="body">
    <div class="layer">
      <div class="side-logo">
        <img src="logo.png" alt="logo" />
      </div>
      <div class="side-form">
        <form action="#" method="post">
          <div class="title">
            <h1>Store Food Game</h1>
            <h2>Recuperar senha de acesso</h2>
          </div>
          <div class="input">
            <input type="email" name="email" autocomplete="off" required />
            <label for="email">E-mail</label>
          </div>
          <button type="submit">Enviar</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "recuperar-senha"
};
</script>

<style lang="css" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.body {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.layer {
  width: 850px;
  height: 426px;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 1px 1px 6px 0 rgba(0, 0, 0, 0.5);

  display: grid;
  grid-template-columns: 1fr 1fr;
}

.layer .side-logo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.layer .side-form {
  color: #0a8037;
}

.layer .side-form form {
  width: 100%;
  max-width: 400px;
  height: 362px;

  margin: 32px auto;
  padding: 32px 44px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.layer .side-form form .title h1 {
  font-size: 32px;
  font-weight: bold;
  text-transform: uppercase;
  margin-bottom: 10px;
  color: #79aa07;
}

.layer .side-form form .title h2 {
  font-size: 20px;
  font-weight: bold;
}

.layer .side-form form .input {
  position: relative;
}

input,
button {
  width: 100%;
  padding: 16px 0;

  border: none;
  border-bottom: 2px solid #0a8037;

  font-size: 18px;
  font-weight: bolder;

  color: black;
  background-color: transparent;

  outline: none;
}

button {
  background-color: #0a8037;
  border-radius: 10px;
  transition: 0.4s;
  color: #fff;
}

button:hover {
  filter: brightness(0.7);
}

input ~ label {
  position: absolute;
  top: 16px;
  left: 0;

  font-size: 1.1rem;

  color: rgba(0, 0, 0, 0.6);

  transition: 0.4s;
}

input:focus ~ label,
input:valid ~ label {
  transform: translateY(-24px);
  font-size: 0.8rem;
  letter-spacing: 0.1rem;
}

@media (max-width: 860px) {
  .layer {
    grid-template-columns: 1fr;
    width: 780px;
  }
  .layer .side-logo {
    display: none;
  }
}

@media (max-width: 415px) {
  .layer {
    height: 440px;
  }
  .layer .side-form {
    display: flex;
  }
  .layer .side-form form {
    max-width: 390px;
    justify-content: space-between;
  }
}
</style>
