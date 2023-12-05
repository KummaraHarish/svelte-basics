<script>
 // export let message;
 export let showModel= false;
export let isPromo = false;
</script>

{#if showModel}
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="backdrop" class:promo={isPromo} on:click|self>
  <div class="model">
    <slot></slot>
    <!--<slot name="title"></slot>
    <p>{message}</p>-->
  </div>
  

</div>
{/if}



<main>

</main>



<style>
  .backdrop{
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0,0.8);
  }
  .model{
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    text-align: center;
    background: white;

  }
  .promo .model{
    background: crimson;
    color: white;
  }

</style>