<<template>
  
    
</template>
<<script>
import Board from "@/utils/board"
export default {
  name: 'board',
  components: {},
  computed: {},
  methods: {

  }
  },
  data (){
      return {
          grid: [],
          gridSize : 4
      }
  
  },
  created () {
      board.init(this.gridSize)
      this.grid =board.square
  }
}
</script>
<<style>

</style>

