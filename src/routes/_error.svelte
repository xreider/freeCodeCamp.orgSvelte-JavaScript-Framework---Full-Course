<script>
  export let status
  export let error
  const dev = process.env.NODE_ENV === 'development'
</script>

<h1>{status}</h1>
<!-- {#if status == '404'} -->
<div class="container">
  <article class="message is-warning">
    <div class="message-header">
      <p>{error.message}</p>
    </div>
    <div class="message-body">
      <a href="/">Click here</a> to go back home.
    </div>
  </article>
</div>
<!-- {/if} -->

{#if dev && error.stack}
  <pre>{error.stack}</pre>
{/if}

<svelte:head>
  <title>{status}</title>
</svelte:head>

<style>
  h1,
  p {
    margin: 0 auto;
  }

  h1 {
    font-size: 2.8em;
    font-weight: 700;
    margin: 0 0 0.5em 0;
  }

  p {
    margin: 1em auto;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 4em;
    }
  }
</style>
