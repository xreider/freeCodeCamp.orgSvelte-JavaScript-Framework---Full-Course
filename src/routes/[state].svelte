<script context="module">
  import requests from '../data/requests'
  import stateNames from '../data/stateNames.js'
  export async function preload(page, session) {
    const state = page.params['state']
    if (stateNames.find((s) => s.abbreviation === state) === undefined) {
      this.error(404, 'State Not Found')
      return
    }
    try {
      const stats = await requests.stateStats(state)
      return { state, stats }
    } catch (e) {
      console.log(e)
      this.error(500, e.message)
      return
    }
  }
</script>

<script>
  import CovidChart from '../components/CovidChart.svelte'
  import CovidStat from '../components/CovidStat.svelte'
  export let state, stats
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

<CovidStat {...stats} />
<CovidChart />

<svelte:head>
  <title>Covid 19 {state}</title>
</svelte:head>
