<template>
  <div class="card border-0">
    <h6 class="card-header bg-white rounded-0 border-0 nes blue">Testnet</h6>
    <div class="card-body pe-5 py-3 bg-blue">
      <button v-clipboard:copy="$parent.endpoint" class="nes-btn is-normal copy copy-content d-inline-block py-0 nes">Copy</button>
      <div class="pe-5">
        <code class="text-white">{{ $parent.endpoint }}</code>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WssUrl',
  components: {
  },
  data () {
    return {
    }
  },
  async mounted () {
  }
}
</script>

<style lang="scss" scoped>
</style>
