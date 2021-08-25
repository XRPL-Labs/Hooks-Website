<template>
  <div>
    <h6 class="card-header bg-white rounded-0 border-0 nes text-white">Hooks</h6>
    <div class="card mb-4 border-0">
      <h3 class="card-header rounded-0 border-0 h6 nes bg-light-card-header blue">
        <button v-clipboard:copy="JSON.stringify(ledgerInfo, null, 2)" class="nes-btn is-normal copy d-inline-block py-0 nes" :class="{'is-disabled': ledgerInfo === 'Connecting...'}">Copy</button>
        Last ledger
      </h3>
      <div class="card-body pe-5 bg-light-card">
        <vue-json-pretty :data="ledgerInfo"></vue-json-pretty>
      </div>
    </div>
  </div>
</template>

<script>
import { XrplClient } from 'xrpl-client'
import VueJsonPretty from 'vue-json-pretty'
import 'vue-json-pretty/lib/styles.css'

export default {
  name: 'LastLedger',
  components: {
    VueJsonPretty
  },
  data () {
    return {
      ledgerInfo: 'Connecting...',
      connection: null
    }
  },
  async mounted () {
    this.connection = await new XrplClient(this.$parent.endpoint)
    this.connection.on('ledger', ledger => {
      this.ledgerInfo = {
        ledger_index: ledger.ledger_index,
        ledger_time: ledger.ledger_time,
        txn_count: ledger.txn_count,
        validated_ledgers: ledger.validated_ledgers,
        type: ledger.type,
        ledger_hash: ledger.ledger_hash,
        ...ledger
      }
    })
  }
}
</script>

<style lang="scss" scoped>
</style>
