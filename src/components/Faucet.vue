<template>
  <div class="card border-0">
    <h6 class="card-header bg-white rounded-0 border-0 nes blue">
      Hooks<sup class="bg-warning text-dark px-1"><small>Testnet</small></sup>
      Faucet</h6>
    <div class="card-body py-3 pt-1 bg-blue">
      <button @click="getSome" v-if="faucet.Address !== '-'" style="margin-top: -2px" class="nes-btn is-primary copy d-inline-block py-0 nes">Again</button>
      <div class="">
        <div v-if="error !== ''" class="col-12">
          <p class="text-center alert alert-danger px-2 py-1 mt-2 mb-2 shadow-sm rounded-0">{{ error[0].toUpperCase() + error.slice(1) }}</p>
        </div>
        <div v-if="faucet.Address === '-'" class="text-center"><button @click="getSome" class="nes-btn py-0 my-3 mt-4 nes btn-lg">Get Some</button></div>
        <div v-if="faucet.Address !== '-'" class="row">

          <div class="pt-2 col-12 col-sm-3 col-lg-3 col-xl-3 border-0 nes"><small><small>Address</small></small></div>
          <div class="pt-2 col-9 col-sm-6 col-lg-6 col-xl-7 border-0 ps-3"><div class="no-overflow"><a class="text-white" :href="link(faucet.Address)" target="_blank">{{ faucet.Address }}</a></div></div>
          <div class="pt-2 col-3 col-sm-3 col-lg-3 col-xl-2 text-end border-0"><button v-clipboard:copy="faucet.Address" class="nes-btn is-normal copy local d-inline-block py-0 ms-0 mr-2 my-0 nes">Copy</button></div>

          <div class="pt-2 col-12 col-sm-3 col-lg-3 col-xl-3 border-0 nes"><small><small>Secret</small></small></div>
          <div class="pt-2 col-9 col-sm-6 col-lg-6 col-xl-7 border-0 ps-3"><div class="no-overflow">{{ faucet.Secret }}</div></div>
          <div class="pt-2 col-3 col-sm-3 col-lg-3 col-xl-2 text-end border-0"><button v-clipboard:copy="faucet.Secret" class="nes-btn is-normal copy local d-inline-block py-0 ms-0 mr-2 my-0 nes">Copy</button></div>

          <div class="pt-2 col-12 col-sm-3 col-lg-3 col-xl-3 border-0 nes"><small><small>TX</small></small></div>
          <div class="pt-2 col-9 col-sm-6 col-lg-6 col-xl-7 border-0 ps-3"><div class="no-overflow"><a class="text-white" :href="link(faucet.TX)" target="_blank">{{ faucet.TX }}</a></div></div>
          <div class="pt-2 col-3 col-sm-3 col-lg-3 col-xl-2 text-end border-0"><button v-clipboard:copy="faucet.TX" class="nes-btn is-normal copy local d-inline-block py-0 ms-0 mr-2 my-0 nes">Copy</button></div>

          <div class="pt-2 col-12 col-sm-3 col-lg-3 col-xl-3 border-0 nes"><small><small>XRP</small></small></div>
          <div class="pt-2 col-9 col-sm-6 col-lg-6 col-xl-7 border-0 ps-3"><div class="no-overflow">{{ faucet.XRP }}</div></div>
          <div class="pt-2 col-3 col-sm-3 col-lg-3 col-xl-2 text-end border-0"></div>

          <div class="pt-2 col-12 col-sm-3 col-lg-3 col-xl-3 border-0 nes"><small><small>Result</small></small></div>
          <div class="pt-2 col-9 col-sm-6 col-lg-6 col-xl-7 border-0 ps-3"><div class="no-overflow">{{ faucet.Result }}</div></div>
          <div class="pt-2 col-3 col-sm-3 col-lg-3 col-xl-2 text-end border-0"></div>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Faucet',
  components: {
  },
  data () {
    return {
      error: '',
      faucet: {
        Address: '-',
        Secret: '-',
        XRP: 0,
        TX: '-',
        Result: '-'
      }
    }
  },
  methods: {
    link (data) {
      return 'https://hooks-testnet-explorer.xrpl-labs.com/' + data
    },
    async getSome () {
      const cors = process.env.NODE_ENV.match(/dev/i)
        ? 'https://cors-anywhere.herokuapp.com/'
        : ''
      const call = await window.fetch(cors + 'https://hooks-testnet.xrpl-labs.com/newcreds', { method: 'POST' })
      const data = await call.json()

      if (typeof data?.error !== 'undefined') {
        this.error = data.error
      } else {
        this.error = ''
        this.faucet.Address = data.address
        this.faucet.Secret = data.secret
        this.faucet.XRP = data.xrp
        this.faucet.TX = data.hash
        this.faucet.Result = data.code
      }
    }
  },
  async mounted () {
  }
}
</script>

<style lang="scss" scoped>
  button.copy.local {
    font-size: .5em;
    position: relative;
    right: 0;
    top: 0;
  }
  .no-overflow {
    display: block;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
</style>
