<script>
  import logo from "./assets/LaughingMan.svg"
  /* Connect2ic utilities */
  import { createClient } from "@connect2ic/core"
  import { defaultProviders } from "@connect2ic/core/providers"
  import { ConnectButton, ConnectDialog, Connect2ICProvider } from "@connect2ic/svelte"
  import "@connect2ic/core/style.css"
  /* IC Canisters */
  import * as dao from "../.dfx/local/canisters/dao"
  import * as ledger from "../.dfx/local/canisters/ledger"
  /* Svelte Components */
  import Profile from "./components/Profile.svelte"
  import Support from "./components/Support.svelte"

  /* TODO */
  /* import Counter from "./components/Proposals.svelte" */

  const client = createClient({
    canisters: {
      dao,
      ledger,
    },
    providers: defaultProviders,
    globalProviderConfig: {
      dev: import.meta.env.DEV,
    },
  })

</script>

<Connect2ICProvider client={client}>
  <div class="App">
    <div class="auth-section">
      <ConnectButton />
    </div>
    <ConnectDialog />
    <header class="App-header">
      <img src={logo} class="App-logo" alt="logo" />
      <p class="slogan">
        roadmap<br>&nbsp;&nbsp;DAO<br>
      </p>
    </header>
    <p class="description">
      guvf qnb vf zrnag gb rynobengr naq znantr n ebnqznc guebhtu n
      pbafrafhf orgjrra vgf hfref - gubfr hfref pna fhozvg naq ibgr sbe
      cebcbfnyf gung jvyy pbafgvghgr gur ebnqznc - gubfr hfref pna nyfb
      ibgr gb hcqngr gur rkvfgvat ebnqznc naq zbqvsl gur cevbevgl beqre,
      erzbir n gnfx be znex vg nf qbar - urer gur ohvyqvat ebnqznc vf gur
      bja ebnqznc bs guvf cebwrpg ohg bapr vg vf pbzcyrgrq vg pna or hfrq
      ol nal bgure cebwrpg gung jvfurf gb qryrtngr vgf ebnqznc gb vgf
      hfref
    </p>
    <div class="dashboard">

      <Profile />
      <Profile />
      <Support />

    </div>
  </div>
</Connect2ICProvider>

<style global>
  body {
    margin: 0;
    font-family: 'SF Mono', SFMono-Regular, ui-monospace,
      'DejaVu Sans Mono', Menlo, Consolas, monospace;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #424242;
  }

  button {
    font-weight: 600;
  }

  .slogan {
    font-size: 1.5em;
    margin-bottom: 0;
  }

  .App-logo {
    height: 35vmin;
    pointer-events: none;
    transform: scale(1);
    animation: pulse 10s infinite;
    margin-top: 1em;
    margin-right: -1.7em;
    margin-bottom: -1.5em;
  }

  .disconnected {
    font-size: 1.3em;
    color: #ff9e9e;
  }

  .demo-button {
    background: #a02480;
    padding: 0 1.3em;
    margin-top: 1em;
    border-radius: 60px;
    font-size: 0.7em;
    height: 35px;
    outline: 0;
    border: 0;
    cursor: pointer;
    color: white;
  }

  .demo-button:active {
    color: white;
    background: #979799;
  }

  .App-header {
    height: calc(60vh);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: calc(15px + 2vmin);
  }

  .dashboard {
    display: grid;
    grid-gap: 30px;
    grid-template-columns: 1fr 1fr 1fr;
  }

  .description {
    font-size: 1.2em;
    text-align: left;
    margin-top: 0em;
    padding: 0em 4em;
  }

  .connected {
    padding: 2em;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-radius: 15px;
  }

  .auth-section {
    padding: 2em;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    text-align: right;
    position: fixed;
    top: 0;
    right: 0;
  }

  @keyframes pulse {
    0% {
      transform: scale(0.97);
      opacity: 0;
    }

    70% {
      transform: scale(1);
      opacity: 1;
    }

    100% {
      transform: scale(0.97);
      opacity: 0;
    }
  }
</style>
