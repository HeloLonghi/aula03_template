<script setup>
  

    const nome = `Heloisa`
    const idade = 16

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }

    import { ref } from 'vue'

    const contador = ref(0)

    function incrementar() {
        contador.value++
  }

    function decrementar() {
        contador.value--
  }
</script>

<template>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações de {{ nome }} na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome).toUpperCase() }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>

    <div class="contador">
        <h2>Contador da Heloisa</h2>
        <p>Valor do contador: {{ contador }}</p>
        <button v-on:click="incrementar">+</button>
        <button @click="decrementar">-</button>

        <div class="valor" :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }">
          <p v-if="contador > 10">Valor maior que 10</p>
          <p v-else>Valor menor que 10</p>
        </div>
    </div>
</template>

<style scoped>
.info {
  background-color: rgb(105, 10, 62);
  padding: 20px 30px;
  margin: 2vw 0;
  color: rgb(218, 236, 241);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

.contador {
  background-color: rgb(105, 10, 62);
  padding: 20px 30px;
  color: rgb(218, 236, 241);
  border-radius: 10px;
}

h2 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

.valor {
  border-radius: 20px;
  text-align: center;
}

</style>

