<template>
    <div class="grid-test">
        <div class="wrapper">
            <div class="col1 row1 colspan1 rowspan1">A</div>
            <div class="box b">B</div>
            <div class="box c">C</div>
            <div class="box d">D</div>
            <div class="box e">E</div>
            <div class="box f">F</div>
        </div>
    </div>
</template>

<script>
export default {
  name: "CodeTableEditView",
  props: {
    msg: String
  },
  created() {
    var style = document.getElementById("css-grid").innerHTML;
    var cols = 12;
    var rows = 50;
    var col;
    for (col = 1; col < cols + 1; col++) {
      style =
        style +
        "\n.grid" +
        col +
        " { display: -ms-grid; -ms-grid-columns: (1fr)[" +
        col +
        "]; -ms-grid-rows: auto; }";
      style = style + "\n.col" + col + " { -ms-grid-column: " + col + "; }";
    }
    var row;
    for (row = 1; row < rows + 1; row++) {
      style = style + "\n.row" + row + " { -ms-grid-row: " + row + "; }";
    }
    var colspan;
    for (colspan = 1; colspan < cols + 1; colspan++) {
      style =
        style +
        "\n.colspan" +
        colspan +
        " { -ms-grid-column-span: " +
        colspan +
        "; }";
    }
    var rowspan;
    for (rowspan = 1; rowspan < rows + 1; rowspan++) {
      style =
        style +
        "\n.rowspan" +
        rowspan +
        " { -ms-grid-row-span: " +
        rowspan +
        "; }";
    }
    // document.getElementById("css-grid").innerHTML = style;
    // console.log(document.getElementById("css-grid").innerHTML);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
    .wrapper {
        display: grid;
        grid-template-columns: 33% 10px 33% 10px 33%;
        grid-template-rows: 200px 10px 300px;
        background-color: #fff;
        color: #444;
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
        grid-column-start: 1;
        grid-column-end: 2;
        grid-row-start: 1;
        grid-row-end: 2;
    }
    .b {
        grid-column-start: 3;
        grid-column-end: 4;
        grid-row-start: 1;
        grid-row-end: 2;
    }
    .c {
        grid-column-start: 5;
        grid-column-end: 6;
        grid-row-start: 1;
        grid-row-end: 2;
    }
    .d {
        grid-column-start: 1;
        grid-column-end: 2;
        grid-row-start: 3;
        grid-row-end: 4;
    }
    .e {
        grid-column-start: 3;
        grid-column-end: 4;
        grid-row-start: 3;
        grid-row-end: 4;
    }
    .f {
        grid-column-start: 5;
        grid-column-end: 6;
        grid-row-start: 3;
        grid-row-end: 4;
    }
    $columns: 12;
    $rows: 50;

    @mixin col-x {
        @for $i from 1 through $columns {
            .col#{$i} { grid-column: $i }
        }
    }

    @mixin grid-x {
        @for $i from 1 through $columns {
            .grid#{$i} { display: grid; grid-template-columns: (1fr)[$i]; }
        }
    }

    @mixin row-x {
        @for $i from 1 through $rows {
            .row#{$i} { grid-row: $i; }
        }
    }

    @mixin colspan-x {
        @for $i from 1 through $columns {
            .colspan#{$i} { grid-column-span: $i; }
        }
    }

    @mixin rowspan-x {
        @for $i from 1 through $rows {
            .rowspan#{$i} { grid-row-span: $i; }
        }
    }

    @include col-x;
    @include grid-x;
    @include row-x;
    @include colspan-x;
    @include rowspan-x;


</style>
