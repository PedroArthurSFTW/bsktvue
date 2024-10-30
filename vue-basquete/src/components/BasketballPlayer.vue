<template>
  <div>
    <h1>Cadastro de Jogadores de Basquete</h1>
    <div>
      <input v-model="newPlayer.name" placeholder="Nome do Jogador">
      <input v-model="newPlayer.team" placeholder="Time">
      <input v-model="newPlayer.position" placeholder="Posição">
      <button @click="addPlayer">Adicionar Jogador</button>
    </div>

    <div v-if="players.length === 0">
      <p>Nenhum jogador cadastrado.</p>
    </div>

    <ul v-else>
      <li v-for="(player, index) in players" :key="index">
        {{ player.name }} - {{ player.team }} - {{ player.position }}
        <button @click="removePlayer(index)">Deletar</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newPlayer: {
        name: '',
        team: '',
        position: '',
      },
      players: []
    };
  },
  methods: {
    addPlayer() {
      if (this.newPlayer.name && this.newPlayer.team && this.newPlayer.position) {
        this.players.push({ ...this.newPlayer });
        this.newPlayer.name = '';
        this.newPlayer.team = '';
        this.newPlayer.position = '';
      } else {
        alert('Por favor, preencha todos os campos.');
      }
    },
    removePlayer(index) {
      this.players.splice(index, 1);
    }
  }
};
</script>

<style scoped>
input {
  margin: 5px;
  padding: 5px;
}
button {
  margin: 5px;
  padding: 5px;
  cursor: pointer;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 10px 0;
}
</style>