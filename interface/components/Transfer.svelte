<script>
  import { useWallet, useTransfer } from "@connect2ic/svelte"

  const [wallet] = useWallet()
  const [transfer] = useTransfer({
    to: "ekh7g-vbiz6-l5bgc-jj2uz-llf2k-f77bb-cr44c-z2bfq-xkwns-ekhyx-dqe",
    amount: Number(0.01),
  })

  const onPurchase = async () => {
    const { height } = await transfer()
  }
</script>
<div class="example">
  {#if $wallet}
    <p>Buy me a beer</p>
    <button class="connect-button" on:click={onPurchase}>Purchase</button>
  {:else}
    <p class="example-disabled">Connect with a wallet to access this example</p>
  {/if}
</div>
