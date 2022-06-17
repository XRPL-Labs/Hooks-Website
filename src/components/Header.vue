<template>
  <div id="nav-component">
    <nav class="navbar navbar-expand-lg" aria-label="Header">
      <a class="navbar-brand blue nes" href="#">
        XRPL Hooks Amendment
        <span class="nes-badge beta d-inline-block">
          <span class="is-error text-dark bg-warning">BETA</span>
        </span>
      </a>
    </nav>

    <div class="float-md-end action-buttons">
      <a href="https://dev.to/t/xrplhooks/top/infinity" target="_blank" class="nes me-3 btn-sm py-1 nes-btn is-warning">Blogs</a>
      <a href="https://github.com/XRPL-Labs/xrpld-hooks/blob/hooks-ssvm/README.md" target="_blank" class="nes nes-btn btn-sm py-1 is-primary alt-color">Quickstart</a>
    </div>

    <div class="nav-scroller nes mb-4">
      <nav class="nav nav-underline" aria-label="Navigation">
        <a class="ps-0 pe-4 me-3 text-dark nav-link active" href="http://hooks-testnet-explorer.xrpl-labs.com" target="_blank">Explorer</a>
        <!-- <a class="ps-0 pe-4 me-3 text-dark nav-link" href="https://hooks-testnet.xrpl-labs.com/faucet" target="_blank">
          Faucet
        </a> -->
        <!-- <span class="badge bg-light shadow-sm text-dark align-text-bottom">27</span> -->
        <a class="ps-0 pe-4 me-3 text-dark nav-link" href="https://github.com/XRPL-Labs/xrpld-hooks/tree/hooks-ssvm/hook-api-examples" target="_blank">Examples</a>
        <a class="ps-0 pe-4 me-3 text-dark nav-link" href="https://xrpl-hooks.readme.io" target="_blank">Docs</a>
        <a class="nav-link pe-4 me-3 text-dark" href="https://github.com/XRPL-Labs/xrpld-hooks" target="_blank">
          <i class="fab fa-2x fa-github-square"></i> Github
        </a>
      </nav>
    </div>

    <div class="alert alert-danger text-center">
      <div class="-h5">
        <span class="fw-bold">
          Warning! This is the Hooks V1 testnet. The Hooks V1 network is deprecated and has been replaced with
          the <a href="https://hooks-testnet-v2.xrpl-labs.com/"><b><u>Hooks V2 staging network</u></b></a>.
        </span>
        If you are about to use V1 or still using V1, please switch to V2. The Hooks V1 testnet will be
        taken offline at August 1st, 2022.
      </div>
    </div>

    <p class="alert alert-primary border-primary bg-light-card-header blue-border rounded-0 shadow-sm px-3 py-2 mb-4">
      Hooks are small, efficient <b>WebAssembly modules</b> designed specifically for the XRPL.
      <a target="_blank" href="https://coil.com/p/XUMM/XRPL-Labs-is-working-on-the-transaction-HOOKS-amendment-for-the-XRP-Ledger-Supporting-business-logic/kEmqhoqMW"><u><b>Read more about Hooks in the announcement blog post.</b></u></a>
      Hooks can be written in any language (compilable to WebAssembly) and most business
      logic and most <b>smart contract concepts</b> can be implemented in a hook.
      <b><a href="https://xrpl-labs.com" target="_blank"><i class="fas fa-rocket"></i> <u>Development by XRPL Labs</u></a></b>
    </p>
  </div>
</template>

<script>
export default {
  name: 'Header',
  components: {
  },
  mounted () {
  }
}
</script>

<style lang="scss" scoped>
  .action-buttons {
    button {
      font-size: .65em;
    }
  }
  .nes-badge.beta {
    margin-top: 0.3em;
    margin-left: -0.8em;
    transform: scale(0.8);
    width: 6em;
    font-size: .6em;
  }
  .navbar-brand.blue {
    white-space: normal;
  }
  a.nav-link {
    .fa-2x {
      margin-top: -1em;
      position: relative;
      top: 0.1em;
      margin-right: -0.15em;
      margin-left: -0.5em;
    }
  }
  button.is-primary {
    &.alt-color {
      background-color: #183FB7;
      &:after {
        box-shadow: inset -4px -4px darken(#183FB7, 10%);
      }
      &:active:not(.is-disabled) {
        &:after {
          box-shadow: inset 4px 4px darken(#183FB7, 10%);
        }
      }
    }
  }
</style>
