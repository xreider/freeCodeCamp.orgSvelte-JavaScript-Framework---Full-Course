<script context="module">
  import requests from '../data/requests'
  export async function preload({ params }) {
    try {
      const usStats = await requests.usStats()
      return { usStats }
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
  import TableContainer from '../components/TableContainer.svelte'
  import Error from './_error.svelte'

  export let usStats
  console.log(usStats, 'usStats')
</script>

<div class="section header">
  <div class="container">
    <h1>Covid 19 Us Tracker</h1>
    <p>
      The data for this site came from <a href="https://covidtracking.com/">
        Covid Tracking
      </a>.
    </p>
  </div>
</div>

<CovidStat {...usStats} />
<CovidChart />
<TableContainer />

<svelte:head>
  <title>Covid 19 Us Tracker</title>
</svelte:head>
