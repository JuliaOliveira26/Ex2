<script setup>
  import{ ref } from 'vue' 
    const nome = 'Julia'
    const idade = 16
    const contador = ref(0)

    function inverter(texto) {
        return texto.split('').reverse().join('')

    }
    function inverterMaiuscula(texto) {
      return inverter(texto).toUpperCase()
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }
</script>

<template>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome) }} </p>
        <p>Nome invertido em maiuscula:{{ inverterMaiuscula(nome) }}
        </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
    <div class="info">
      contador:{{ contador }}
      <button @click="contador++">+</button>
      <button @click="contador--">-</button>
      <div v-if="contador> 10" class="verde">E maior que 10</div>
    <div v-else-if="contador <10" class="vermelho">é menor que 10</div>
    <div v-else class="amarelo">E 10 </div>
    </div>
    

</template>

<style scoped>
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin: 0 20px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
.verde{
  color: green;
}
.vermelho{
  color: red;
}
.amarelo{
  color: yellow;
}

</style>