<script>
  export let cases,
    deaths,
    recovered,
    ventilator,
    hospitalized,
    icu,
    tested,
    updated
</script>

<h1>CovidStat</h1>

<div class="section">
  <div class="container">
    <div class="columns">
      <h2 class="is-3 column">Cases: {cases}</h2>
      <h2 class="is-3 column">Deaths: {deaths}</h2>
      <h2 class="is-3 column">Recovered: {recovered}</h2>
      <h2 class="is-3 column">Updated: {updated}</h2>
    </div>
  </div>
</div>

<div class="section">
  <div class="container">
    <div class="columns">
      <h2 class="is-3 column">Tested: {tested}</h2>
      <h2 class="is-3 column">Hospitalized: {hospitalized}</h2>
      <h2 class="is-3 column">Total ICU: {icu}</h2>
      <h2 class="is-3 column">Total Ventilator: {ventilator}</h2>
    </div>
  </div>
</div>

<style>
  .columns {
    border: 1px solid black;
  }
</style>
