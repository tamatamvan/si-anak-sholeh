<template>
  <div>
    <h1>Zaenal</h1>
    <p>Uang saku: {{ jatahUangSaku }}</p>
    <button type="button" @click="jajan">Jajan</button>
    <br>
    <input type="text" v-model="duitBuatDiTrfKeBapak">
    <button type="button" @click="balasBudi">Balas Budi</button>
  </div>
</template>

<script>
export default {
  props: ['uangSaku'],
  data () {
    return {
      duitBuatDiTrfKeBapak: null
    }
  },
  computed: {
    jatahUangSaku () {
      return this.uangSaku * 40 / 100
    }
  },
  methods: {
    jajan () {
      this.$emit('jajan')
    },
    balasBudi () {
      let payloadDuit = parseInt(this.duitBuatDiTrfKeBapak)
      this.$emit('transferDuit', payloadDuit)
    }
  }
}
</script>

<style>

</style>
