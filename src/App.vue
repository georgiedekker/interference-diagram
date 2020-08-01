<template>
  <v-app id="app">
    <v-main>
      <v-app-bar dense>
        <v-app-bar-nav-icon href="#">
          <v-img max-height="20" max-width="40" src="./assets/ReEngine_Logo_Web.png"></v-img>
        </v-app-bar-nav-icon>
        <v-toolbar-title>
          <b>
            <a href="https://www.reengineconsulting.com/" target="_blank">ReEngine Consulting</a>
          </b> presents
          <b>Interference Diagram</b>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-title>Interference Diagram</v-toolbar-title>
        <v-btn icon>
          <v-icon href="https://www.reengineconsulting.com/" target="_blank">mdi-domain</v-icon>
        </v-btn>
        <v-btn icon href="https://www.linkedin.com/in/georgedekker/" target="_blank">
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-app-bar>
      <v-col fluid>
      <v-row>
      <Boards id=boards-1>
        <Board id=board-1 draggable="true">
          <Card id="card-1" draggable="true">
          </Card>
        </Board>
        </Boards>
        <Boards id=boards-2>
        <Board id=board-2 draggable="true">
          <Card id="card-2" draggable="true">
          </Card>
        </Board>
        </Boards>
        <Boards id=boards-3>
        <Board id=board-3 draggable="true">
          <Card id="card-3" draggable="true">
          </Card>
        </Board>
        </Boards>
      </v-row>
      <v-row>
        <Boards id=boards-4>
        <Board id=board-4 draggable="true">
          <Card id="card-4" draggable="true">
          </Card>
        </Board>
        </Boards>
        <Boards id=boards-5>
        <Board id=board5 draggable="true">
          <Card id="board" draggable="true">
          </Card>
        </Board>
        </Boards>
         <Boards id=boards-6>
        <Board id=board-6 draggable="true">
          <Card id="card-6" draggable="true">
          </Card>
        </Board>
        </Boards>
      </v-row>
      <v-row>
        <Boards id=boards-7>
        <Board id=board-7 draggable="true">
          <Card id="card-7" draggable="true">
          </Card>
        </Board>
        </Boards>
        <Boards id=boards-8>
        <Board id=board-8 draggable="true">
          <Card id="card-8" draggable="true">
          </Card>
        </Board>
        </Boards>
        <Boards id=boards-9>
        <Board id=board-9 draggable="true">
          <Card id="card-9" draggable="true">
          </Card>
        </Board>
        </Boards>
      </v-row>
        </v-col>      
    </v-main>
    <v-footer fixed="fixed" app>
              <span>&copy; 2020 - Made with 💙 by by <a href="https://www.linkedin.com/in/georgedekker/" target="_blank">George Dekker</a> for <a href="https://www.reengineconsulting.com/" target="_blank">ReEngine Consulting</a></span>
            </v-footer>
  </v-app>
</template>

<script>
import Boards from "./components/Boards.vue";
import Board from "./components/Board.vue";
import Card from "./components/Card.vue";
export default {
  name: "App",
  // data: {
  //   boardsList: [
  //     {id: 'board-1'},
  //     {id: 'board-2'}
  //   ]
  // },
  components: {
    Boards,
    Board,
    Card,
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
.boards {
  margin-bottom: 40px;
  padding-bottom: 100px;
  /* padding-top: 100px; */
}
.board {
  /* margin-bottom: 20px; */
  padding-bottom: 100px;
}
</style>
