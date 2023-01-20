<script>
  import { useWallet, useBalance } from "@connect2ic/svelte"

  const [wallet] = useWallet()
  const [assets] = useBalance()
</script>
<div class="connected">
  {#if $wallet}
    <p>Wallet address: <span style="font-size: 0.7em">{$wallet.principal}</span></p>
    <table>
      <tbody>
        {#if $assets}
          {#each $assets as asset}
            <tr>
              <td>
                {asset.name}
              </td>
              <td>
                {asset.amount}
              </td>
            </tr>
          {/each}
        {/if}
      </tbody>
    </table>
  {:else}
    <p class="disconnected">disconnected</p>
  {/if}
</div>
