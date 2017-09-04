<template>
  <div>
    <h1>Abang Nasikin</h1>
    <p>Uang saku: {{ jatahUangSaku }}</p>
    <p>Sumbangan: {{ rezekiSumbangan }}</p>
  </div>
</template>

<script>
export default {
  props: ['uangSaku', 'rezekiSumbangan'],
  computed: {
    jatahUangSaku () {
      return this.uangSaku * 60 / 100
    }
  }
}
</script>

<style>

</style>
