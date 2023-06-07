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
        <a class="ps-0 pe-4 me-3 text-dark nav-link active" href="http://hooks-testnet-v3-explorer.xrpl-labs.com" target="_blank">Explorer</a>
        <!-- <a class="ps-0 pe-4 me-3 text-dark nav-link" href="https://hooks-testnet-v3.xrpl-labs.com/faucet" target="_blank">
          Faucet
        </a> -->
        <!-- <span class="badge bg-light shadow-sm text-dark align-text-bottom">27</span> -->
        <a class="ps-0 pe-4 me-3 text-dark nav-link" href="https://github.com/XRPL-Labs/xrpld-hooks/tree/hooks-ssvm/hook-api-examples" target="_blank">Examples</a>
        <a class="ps-0 pe-4 me-3 text-dark nav-link" href="https://xrpl-hooks.readme.io/v3.0" target="_blank">Docs</a>
        <a class="nav-link pe-4 me-3 text-dark" href="https://github.com/XRPL-Labs/xrpld-hooks" target="_blank">
          <i class="fab fa-2x fa-github-square"></i> Github
        </a>
      </nav>
    </div>

    <div class="card shadow-sm mb-3 rounded">
      <div class="card-body rounded" id="builder">
        <div class="row">
          <div class="col-4 col-sm-3 col-lg-2"><img src="https://hooks.xrpl.org/images/hooks-logo.svg" class="img-fluid" /></div>
          <div class="col-8 col-sm-9 col-lg-10">
            <div class="h5"><strong>Develop, test and deploy your Hooks on your browser</strong></div>
            With Hooks Builder you can develop, test, debug and deploy your own Hooks on testnet, using our examples or building your own from scratch.
            <div class="mt-3 text-end">
              <a href="https://hooks.xrpl.org" class="btn nes me-3 py-1 nes-btn is-warning">Start building &raquo;</a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="card shadow-sm mb-3 text-center">
      <div class="card-body alert-primary fw-bold border-top">
        <span class="-h5">To connect to the Hooks V3 Staging net (client, Xumm, node peering), please
        <a href="https://xumm.notion.site/Hooks-V3-staging-net-info-518fa261c5cd49d2bcb89a5b9e7bef05" target="_blank"><b><u>check this page &raquo;</u></b></a></span>
      </div>
      <div class="card-body">
        Hooks are small, efficient <b>WebAssembly modules</b> designed specifically for the XRPL.
        <a target="_blank" href="https://coil.com/p/XUMM/XRPL-Labs-is-working-on-the-transaction-HOOKS-amendment-for-the-XRP-Ledger-Supporting-business-logic/kEmqhoqMW"><u><b>Read more about Hooks in the announcement blog post.</b></u></a>
        Hooks can be written in any language (compilable to WebAssembly) and most business
        logic and most <b>smart contract concepts</b> can be implemented in a hook.
        <b><a href="https://xrpl-labs.com/#team" target="_blank"><i class="fas fa-rocket"></i> <u>Development by XRPL Labs</u></a></b>
      </div>
    </div>
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
  #builder {
    background: linear-gradient(
      49deg,
      rgba(38, 17, 56, 1) 0%,
      rgba(40, 33, 46, 1) 100%
    );
    color: white;
  }
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
