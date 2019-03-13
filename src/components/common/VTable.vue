<template lang="html">
  <div id="v-table">
    <header>
      {{ tableName }}
    </header>
    <table>
      <tr>
        <th v-for="name in Object.keys(list[0])" :key="name">
          {{ name }}
        </th>
      </tr>

      <tr v-for="item in list" :key="item">
        <slot :item="item"/>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'v-table',
  props: ['list', 'tableName']
}
</script>

<style lang="css" scoped>
#v-table {
  width: 500px;
  min-height: 400px;
  background-color: white;
  border: 1px solid lightgrey;
  border-radius: 2px;
  margin: 5px 0;
}
header {
  border-bottom: 1px solid lightgrey;
  text-align: center;
  font-weight: bold;
  color: orange;
}

table {
  width: 100%;
}

tr {
  text-align: center;
}
th {
  text-transform: uppercase;
}
</style>
