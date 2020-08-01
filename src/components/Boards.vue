<template>
<v-col cols="4">
<v-card
    light
    loader-height="200px"
    :id="board_id"
    class="boards"
    @dragover.prevent
    @dragend.prevent="dragEnd"
    @drop.prevent="drop"
  >    
  <v-row>
  <v-col cols="2"></v-col>
  <v-col cols="8"><v-text-field name="name" text-align="center" label="Area" hide-details="auto" filled shaped dense></v-text-field></v-col>
  <v-col cols="2"></v-col>
  </v-row>
        <slot />
     </v-card>
     </v-col>
</template>

<script>
export default {
  props: ["id","board_id"],
  methods: {
    drop: (g) => {
      // console.log(Object.keys(g))
      const board_id = g.dataTransfer.getData("board_id");
      const board = document.getElementById(board_id);
       const card_id = g.dataTransfer.getData("id");
      const card = document.getElementById(card_id);
      // console.log(g.target._prevClass.startsWith('boards')+' '+board)
      // console.log(g.target.className)
    //    if(g.target._prevClass.startsWith('board')){
    //   console.log('dropping on BOARD: '+g.target.className)
    //   console.log('Drop on BOARD: '+g.target._prevClass)
    //   board.style.display = "block"
    //   g.target.appendChild(board)
    // }
      if(card!=null){
      console.log('dropping CARD on BOARDS: '+g.target.className)
      console.log('Drop on BOARDS: '+g.target._prevClass)
      console.log('card: '+card)
      // console.log('dragged CARD on BOARDS: '+board.className)
      // board.className = 'board v-card v-sheet theme--dark'
      // console.log('dragged CARD: '+board.className)
      // board.style.display = "block"
      // g.target.appendChild(board)
    }
    if(g.target._prevClass.startsWith('boards')){
      console.log('dropping on BOARDS: '+g.target.className)
      console.log('Drop on BOARDS: '+g.target._prevClass)
      if(board!=null){
      console.log('dragged BOARD: '+board.className)
      board.style.display = "block"
      g.target.appendChild(board)}
      if(card!=null){
        console.log('dragged CARD: '+card.className)
        card.style.display = "block"
      g.target.appendChild(card)
      }
    }
        },
      // console.log('g: '+g.dataTransfer.getData('board_id'))
      // console.log('checkTrust: '+Object.keys(e))
      // console.log('board_id.target: '+Object.keys(board)+' \n'+Object.keys(g.target)+' \n'+Object.entries(board))
      // console.log('e.target: '+Object.keys(e.target)+' '+Object.keys(e.target.__vue__))
      // // if(document.getElementById(card_id).parentElement!=null){
      // console.log('parent: '+document.getElementById(card_id).parentElement)
      // console.log('parenVuet: '+Object.keys(document.getElementById(card_id).parentElement.__vue__._uid))
      // console.log('parentPrev: '+document.getElementById(card_id).parentElement._prevClass)
    dragEnd: (b) => {
      const board_id = b.dataTransfer.getData("board_id");
      const board = document.getElementById(board_id);
       const card_id = b.dataTransfer.getData("id");
      const card = document.getElementById(card_id);
      const boardTarget = b.target;
       if(!b.target._prevClass.startsWith('boards')){
          if(board!=null){
      b.dataTransfer.setData("board_id", boardTarget.board_id)
      // console.log(b.target.board_id)
      // boardTarget.style.display = "block"
      }
       if(card!=null){
         b.dataTransfer.setData("card_id",boardTarget.id)
        //  boardTarget.style.display = "block"
       }
       }
        setTimeout(() => {
          b.target.style.display = "block";
        }, 0);
    },
  },
};
</script>

<style>

</style>