<script>
  import { useWallet, useTransfer } from "@connect2ic/svelte"

  const [wallet] = useWallet()
  const [transfer] = useTransfer({
    to: "ekh7g-vbiz6-l5bgc-jj2uz-llf2k-f77bb-cr44c-z2bfq-xkwns-ekhyx-dqe",
    amount: Number(0.01),
  })

  const onSupport = async () => {
    const { height } = await transfer()
  }
</script>
<div class="connected">
  {#if $wallet}
    <button class="connect-button" on:click={onSupport}>Contribute</button>
  {:else}
    <p class="disconnected">disconnected</p>
  {/if}
</div>
