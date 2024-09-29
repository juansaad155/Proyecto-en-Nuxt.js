<template>
  <div class="hanoi-container">
    <h1>La Experiencia del Proyecto</h1>
    <p>
      El trabajo fue un poco complicado, ya que sin su guía fue más difícil desarrollarlo.
      Sin embargo, poco a poco, con las herramientas y conocimientos que nos había enseñado,
      pudimos lograr terminar el proyecto. Le pusimos mucho empeño, y en caso de que nuestro
      desempeño en el parcial haya sido regular, esperamos que este trabajo lo compense.
    </p>

    <h2>Juega a las Torres de Hanoi</h2>
    <p>El objetivo es mover todos los discos de la Torre 1 a la Torre 3, siguiendo las reglas:</p>
    <ul>
      <li>Solo se puede mover un disco a la vez.</li>
      <li>Solo puedes mover el disco superior de una torre.</li>
      <li>No puedes colocar un disco grande sobre uno más pequeño.</li>
    </ul>

    <div class="game-board">
      <div v-for="(tower, index) in towers" :key="index" class="tower" 
        @click="selectTower(index)" 
        :class="{ selected: selectedTower === index }">
        <div class="disk" v-for="(disk, i) in tower" :key="i" :style="getDiskStyle(disk)">
          {{ disk }}
        </div>
      </div>
    </div>

    <p>Movimientos: {{ moves }}</p>
    
    <div v-if="gameWon" class="win-message">
      <span v-if="moves === 7">¡Felicidades, eres el mejor!ㅤ</span>
      <span v-else-if="moves < 7">¡Eres Dios?</span>
      <span v-else>¡Felicidades, pero puedes hacerlo en menos movimientos! ㅤ</span>
      <button @click="resetGame">Reiniciar Juego</button>
    </div>
    
    <p>ㅤ ㅤ ㅤ</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      towers: [[3, 2, 1], [], []],
      selectedTower: null,
      moves: 0,
      gameWon: false,
    };
  },
  methods: {
    selectTower(index) {
      if (this.selectedTower === null) {
        this.selectedTower = index;
      } else {
        this.moveDisk(this.selectedTower, index);
        this.selectedTower = null;
        this.checkWin();
      }
    },
    moveDisk(from, to) {
      const fromTower = this.towers[from];
      const toTower = this.towers[to];

      if (fromTower.length > 0) {
        const disk = fromTower[fromTower.length - 1];

        if (toTower.length === 0 || disk < toTower[toTower.length - 1]) {
          toTower.push(fromTower.pop());
          this.moves++;
        }
      }
    },
    getDiskStyle(disk) {
      return {
        width: `${disk * 50}px`,
        backgroundColor: '#1A73E8',
        margin: '5px auto',
        height: '20px',
        borderRadius: '5px',
        textAlign: 'center',
        color: 'white',
      };
    },
    checkWin() {
      if (this.towers[2].length === 3) {
        this.gameWon = true;
      }
    },
    resetGame() {
      this.towers = [[3, 2, 1], [], []];
      this.selectedTower = null;
      this.moves = 0;
      this.gameWon = false;
    },
  },
};
</script>

<style scoped>
.hanoi-container {
  text-align: center;
  margin-top: 20px;
  font-family: 'Roboto', sans-serif;
}

h1 {
  color: #1A73E8;
}

p {
  font-size: 16px;
  line-height: 1.6;
  margin: 15px 0;
}

h2 {
  margin-top: 30px;
  color: #1A73E8;
}

.game-board {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.tower {
  width: 150px;
  height: 300px;
  border: 2px solid #333;
  border-radius: 8px;
  margin: 0 20px;
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  padding: 10px;
  background-color: #F5F5F5;
  cursor: pointer;
}

.tower.selected {
  background-color: #D3E3FC;
}

.disk {
  display: flex;
  justify-content: center;
  align-items: center;
}

.win-message {
  color: rgb(0, 19, 128);
  font-weight: bold;
  margin-top: 20px;
}

button {
  margin-top: 10px;
  padding: 10px 20px;
  background-color: #1A73E8;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #1559b3;
}

ul {
  list-style-type: disc;
  margin-left: 40px;
  text-align: left;
}
</style>