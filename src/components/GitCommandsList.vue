<template>
<div>
  <h2 class="commands-list-title">{{title}}</h2>
  <table>
    <tr>
      <th>Commande</th>
      <th>Description</th>
    </tr>

    <tr v-for="command in commands" v-bind:key="command.command">
      <td>{{command.command}}</td>
      <td>{{command.description}}</td>
    </tr>
  </table>
</div>
</template>

<script>
export default {
  props: [
    'title',
    'commands',
  ],
};
</script>

<style lang="scss">
    .commands-list-title {
        text-transform: uppercase;
    }
</style>