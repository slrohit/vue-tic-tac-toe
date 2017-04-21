<template>
  <div>
    <div> Next Player is <b>{{getCurrentPlayer}}</b></div>
    <div v-for="i in 3" :key="i" class="board-row">
      <Square v-for="j in 3" :key="j" :idx="getSquareIndex(i,j)" ></Square>
    </div>
  </div>
</template>

<script>
import {mapGetters} from 'vuex'
import Square from './Square'
  export default {
    name:'board',
    methods:{
      getSquareIndex(i,j){
        return 3*(i-1) + (j-1)
      }
    },
    components:{
      'Square':Square
    },
    computed: {
      ...mapGetters([
        'getCurrentPlayer'
      ])
    }
  }
</script>
