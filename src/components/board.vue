<<template>
  <TABLE BORDER="1"> 
<CAPTION> 2048 </CAPTION> 
<TR> 
<TH> </TH> 
<TH> </TH> 
<TH> </TH> 
<TH> </TH> 
</TR> 
<TR> 
<TH> </TH> 
<TD> </TD> 
<TD> </TD> 
<TD> </TD> 
</TR> 
</TABLE>   
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

