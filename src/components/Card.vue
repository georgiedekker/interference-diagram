<template>
  <v-card outlined light :id="id" class="card" :draggable="draggable" @dragstart="dragStart">
    <v-card-title><v-text-field name="name" text-align="center" label="Card" hide-details="auto" filled shaped dense></v-text-field></v-card-title>
    <slot />
  </v-card>
</template>

<script>
export default {
  props: ["id", "draggable"],
  methods: {
    dragStart: (e) => {    
      const target = e.target;
      if(e.target._prevClass.startsWith('card')){
      e.dataTransfer.setData("card_id", target.id)}
      setTimeout(() => {
        target.style.display = "none";
      }, 0);
    },
  },
};
</script>

<style>
</style>