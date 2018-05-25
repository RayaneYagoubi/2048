<template>
 <div class="app">
   <h2>Jeu 2048 !</h2>
    <table class="grid">
        <tr class="tile" v-for="(x, index) in Board.squares" :key="index" :index="index">
            <td class="line" v-for="(y, index) in x" :key="index" :index="index">
                <div class="tile-container" v-if="y != 0"
                    v-bind:style="{backgroundColor: y === 2 || y === 4 ? '#d19c00'

                        : y === 8 || y === 16 ? '#ffb805'
                        : y === 32 || y === 64 ? '#fc5c05'
                        : y === 128 || y === 256 ? '#e83f0b'
                        : y === 512 || y === 1024 ? '#ad583e'
                        : '#9b9b9b'}">

                    <span class="number">{{ y }}</span>
                </div>
            </td>
        </tr>
    </table><br><br>
    <table cellpadding="0" cellspacing="0" align="center" style="text-align: center; border: none;">
        <a href="javascript:document.location.href='app.vue'" style="text-decoration: none; color: #000000">
          <tr>
            <td>
              <p style="font-size: 12px; font-family: Arial; color: #000000">
                Nouvelle partie
              </p>
            </td>
          </tr>
         </a>
    </table>
 </div>

</template>
<script>
  import Board from '@/Board'
  export default {

  name: 'app',
  created(){
    window.addEventListener('keyup', this.direction);
    Board.init(4);
  },
  data () {
    return {
      Board:Board
    }
  },
  methods: {
    direction: function (event) {
      let touchOk = [38,39,40,37]

      if(touchOk.includes(event.which)) {
        switch (event.which) {
          case 38:
            this.Board.move('left')
            break;
          case 37:
            this.Board.move('up')
            break;
          case 40:
            this.Board.move('right')
            break;
          case 39:
            this.Board.move('down')
            break;
        }

        this.$forceUpdate()
      }
    }
  }

}
</script><!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>

.tile-container{
  width: 50px;
  height: 50px;
  border-radius:7px;
  margin-left: 25%;
  text-align: center;
}

h1, h2 {
  font-weight: normal;
  text-align: center;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

table, td, th {
   border: 1px solid black;
   border-radius:7px;
   margin: auto;
}

td {
  height: 90px;
  width: 90px;
  text-align: center;
}

</style>