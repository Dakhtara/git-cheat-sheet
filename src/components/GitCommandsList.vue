<template>
  <div class="commands-list">
    <h2 class="commands-list-title">{{title}}</h2>
    <table class="commands-list-table">
      <tr v-for="command in commands" v-bind:key="command.command">
        <td class="right-border">{{command.command}}</td>
        <td>{{command.description}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  props: ["title", "commands"],
};
</script>

<style lang="scss">
.commands-list {
    max-width: 100%;
    page-break-inside: avoid;
    break-inside: avoid-page;
      -webkit-column-break-inside: avoid;
}
.commands-list-title {
  text-transform: uppercase;
  color: #58ade3;
  font-size: 16px;
}

.commands-list-table {
    border-top: 2px solid #58ade3;
    border-collapse: collapse;
    width: 100%;
    font-size: 12px;
    break-inside: avoid-page;
    & td, & th {
        padding: 10px;
    }
    tr:nth-child(even) {
        background-color: #F2F2F2;
    }
}

.right-border {
    border-right: 1px solid #aeaeae;
    width: 25%;
}
</style>