<template>
<v-card
  dark
    :id="id"
    class="board"
    :draggable="draggable"
    @dragstart="dragStart"
    @dragover.prevent
    @dragend.prevent="dragEnd"
    @drop.prevent="drop"
  >
  <v-text-field name="name" text-align="center" label="Topic" hide-details="auto" filled shaped dense></v-text-field>
  <!-- <v-card-title>{{ id }}</v-card-title> -->
  
  <slot />
  
  </v-card>
</template>

<script>
export default {
  props: ["id", "draggable", "board_id"],
  methods: {
    dragStart: (f) => {
      const target = f.target;
      // console.log(Object.keys(target.style))
      console.log(f.target._prevClass)
       if(f.target._prevClass.startsWith('board')){
      f.dataTransfer.setData("board_id", target.id)}
      // console.log(f.board_id)
      setTimeout(() => {
        target.style.display = "none";
      }, 0);
    },
    drop: (e) => {
      const card_id = e.dataTransfer.getData("card_id");
      const card = document.getElementById(card_id);
      // console.log(Object.keys(card.style.display))
      // console.log(Object.keys(card_id))
      card.style.display = "block";
      e.target.appendChild(card);
      // console.log('e: '+e.dataTransfer.getData('card_id'))
      // console.log('checkTrust: '+Object.keys(e))
      // console.log('card_id.target: '+Object.keys(card_id)+' '+Object.keys(e.target))
      // console.log('e.target: '+Object.keys(e.target)+' '+Object.keys(e.target.__vue__))
      // // if(document.getElementById(card_id).parentElement!=null){
      // console.log('parent: '+document.getElementById(card_id).parentElement)
      // console.log('parenVuet: '+Object.keys(document.getElementById(card_id).parentElement.__vue__._uid))
      // console.log('parentPrev: '+document.getElementById(card_id).parentElement._prevClass)

      // }
    },
    dragEnd: (b) => {
      const btarget = b.target;
      b.dataTransfer.setData("card_id", btarget.id);
      btarget.style.display = "block";
    },
    //  dragOver: c=>{
    //   console.log('dragOver: '+Object.keys(c))
    //   //  console.log('e.target0: '+Object.keys(c.__vue__))
    // }
    //  dragStart: e =>{
    //   const target = e.target;
    //   console.log('dragstart target: '+target)
    //   e.dataTransfer.setData('card_id', target.id);
    //   setTimeout(() => {
    //     target.style.display = "none";
    //   }, 0);
    // }
  },
};
</script>

<style>
</style>  