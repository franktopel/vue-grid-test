<template>
  <div class="grid-test">
    <div class="wrapper">
      <div class="box a">A</div>
      <div class="box b">B</div>
      <div class="box c">C</div>
      <div class="box d">D</div>
      <div class="box e">E</div>
      <div class="box f">F</div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import "./GridTest.scss"
export default {
  name: 'GridTest',
  props: {
    msg: String
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  .wrapper {
    display: grid;
    grid-template-columns: 4fr 20px 4fr 20px 4fr;
    grid-template-rows: auto;
    background-color: #fff;
    color: #444;
    margin: 10px auto;
    max-width: 1280px;
    appearance: none;
    min-height: 100vh;
  }
  .box {
    background-color: rgb(120,70,123);
    border: 5px solid rgb(88,55,112);
    color: #fff;
    border-radius: 5px;
    padding: 20px;
    font: 150%/1.3 Lucida Grande,Lucida Sans Unicode,Lucida Sans,Geneva,Verdana,sans-serif;
  }
  .a {
    grid-column: 1 / 2;
    grid-row: 1 / 2;
  }
  .b {
    grid-column: 3 / 4;
    grid-row: 1 / 2;
  }
  .c {
    grid-column: 5 / 6;
    grid-row: 1 / 2;
  }
  .d {
    grid-column: 1 / 2;
    grid-row: 3 / 4;
  }
  .e {
    grid-column: 3 / 4;
    grid-row: 3 / 4;
  }
  .f {
    grid-column: 5 / 6;
    grid-row: 3 / 4;
  }

  /*.warn {
    grid-column-end: 3;
    grid: subgrid;
    grid-template-areas:  "head head"
                          "nav  main"
                          "foot ....";
  }*/
</style>


