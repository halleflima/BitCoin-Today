<template>

  <div class="cliente">
    
    <form id="cadCliente" @submit="chegForm" method="post">
      <p>
        <label for="name">Nome</label>
        <input v-model="name" type="text" id="name" />
      </p>

      <p>
        <label for="password">Senha</label>
        <input v-model="password" type="password" id="password" />
      </p>

    </form>

  </div>

</template>

<script>
export default {
  data() {
    return{
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  html{
    background: black;
  }
</style>
