<script context="module">
  export async function preload(page, session) {
    console.log(page)
    return { state: page.params['state'] }
  }
</script>

<script>
  import CovidChart from '../components/CovidChart.svelte'
  import CovidStat from '../components/CovidStat.svelte'
  export let state
</script>

<div class="section header">
  <div class="container">
    <h1>Covid 19 {state}</h1>
    <p>
      The data for this site came from <a href="https://covidtracking.com/">
        Covid Tracking
      </a>.
    </p>
  </div>
</div>

<CovidStat />
<CovidChart />

<svelte:head>
  <title>Covid 19 {state}</title>
</svelte:head>
