<template>
  <div id="app">
    <h2>Saldo Rekening Bapak : {{ saldoRekening }}</h2>
    <Nasikin 
    :uangSaku="saldoRekening" 
    :rezekiSumbangan="duitBuatAbang">
    </Nasikin>
    <Zaenal 
    :uangSaku="saldoRekening" 
    @jajan="kasihDuit"
    @transferDuit="terimaDuit">
    </Zaenal>
  </div>
</template>

<script>
import Nasikin from '@/components/Nasikin'
import Zaenal from '@/components/Zaenal'
export default {
  name: 'app',
  components: {
    Nasikin,
    Zaenal
  },
  methods: {
    showAlert () {
      alert('HIIIIIIIIIII')
    },
    kasihDuit () {
      console.log('Adek mau jajan phahh')
      this.saldoRekening -= 18000
    },
    terimaDuit (payloadDuit) {
      console.log('Anak bapak yang soleh habis trf duit sebesar: ', payloadDuit)
      this.duitBuatAbang += payloadDuit
    }
  },
  data () {
    return {
      msg: 'Hello Jack',
      saldoRekening: 100000,
      duitBuatAbang: null
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
p {
  font-size: 24px;
}
</style>
