<template>
  <main class="container-fluid px-0">
    <div class="row">
      <div class="col-12 col-md-6">
        <WssUrl />
        <Faucet class="mt-3" />
        <!-- <div class="card mt-4 border-0">
          <h3 class="card-header rounded-0 border-0 h6 nes bg-card-header text-white">
            <button v-clipboard:copy="'Something here...'" class="nes-btn is-normal copy d-inline-block py-0 nes">Copy</button>
            Another example
          </h3>
          <div class="card-body text-white pe-5 bg-card">Something here...</div>
        </div> -->

        <!-- <div class="card mt-4 border-0">
          <h3 class="card-header rounded-0 border-0 h6 nes bg-card-header text-white">
            <button v-clipboard:copy="'Something here...'" class="nes-btn is-normal copy d-inline-block py-0 nes">Copy</button>
            Example Hook
          </h3>
          <div class="card-body text-white pe-5 bg-card">Something here...</div>
        </div> -->
      </div>

      <div class="col-12 col-md-6">
        <LastLedger />
      </div>

      <!-- <div class="col-12">
        <div class="my-3 p-3 bg-body rounded shadow-sm">
          <h6 class="border-bottom pb-2 mb-0">Recent updates</h6>
          <div class="d-flex text-muted pt-3">
            <svg class="bd-placeholder-img flex-shrink-0 me-2 rounded" width="32" height="32" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Placeholder: 32x32" preserveAspectRatio="xMidYMid slice" focusable="false"><title>Placeholder</title><rect width="100%" height="100%" fill="#007bff"/><text x="50%" y="50%" fill="#007bff" dy=".3em">32x32</text></svg>

            <p class="pb-3 mb-0 small lh-sm border-bottom">
              <strong class="d-block text-gray-dark">@username</strong>
              Some representative placeholder content, with some information about this user. Imagine this being some sort of status update, perhaps?
            </p>
          </div>
          <div class="d-flex text-muted pt-3">
            <svg class="bd-placeholder-img flex-shrink-0 me-2 rounded" width="32" height="32" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Placeholder: 32x32" preserveAspectRatio="xMidYMid slice" focusable="false"><title>Placeholder</title><rect width="100%" height="100%" fill="#e83e8c"/><text x="50%" y="50%" fill="#e83e8c" dy=".3em">32x32</text></svg>

            <p class="pb-3 mb-0 small lh-sm border-bottom">
              <strong class="d-block text-gray-dark">@username</strong>
              Some more representative placeholder content, related to this other user. Another status update, perhaps.
            </p>
          </div>
          <div class="d-flex text-muted pt-3">
            <svg class="bd-placeholder-img flex-shrink-0 me-2 rounded" width="32" height="32" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Placeholder: 32x32" preserveAspectRatio="xMidYMid slice" focusable="false"><title>Placeholder</title><rect width="100%" height="100%" fill="#6f42c1"/><text x="50%" y="50%" fill="#6f42c1" dy=".3em">32x32</text></svg>

            <p class="pb-3 mb-0 small lh-sm border-bottom">
              <strong class="d-block text-gray-dark">@username</strong>
              This user also gets some representative placeholder content. Maybe they did something interesting, and you really want to highlight this in the recent updates.
            </p>
          </div>
          <small class="d-block text-end mt-3">
            <a href="#">All updates</a>
          </small>
        </div>
      </div> -->
    </div>
  </main>
</template>

<script>
import WssUrl from './WssUrl'
import Faucet from './Faucet'
import LastLedger from './LastLedger'

export default {
  name: 'Body',
  components: {
    WssUrl,
    Faucet,
    LastLedger
  },
  data () {
    return {
      endpoint: 'wss://hooks-testnet.xrpl-labs.com'
    }
  },
  async mounted () {
  }
}
</script>

<style lang="scss">
  button.copy {
    font-size: .6em;
    position: absolute;
    right: 1em;
    top: 0.45em;
    &.copy-content {
      top: 5em;
    }
  }
</style>
