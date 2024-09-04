<!-- Script JS -->
<script>
  /* Importamos d3 para tenerlo disponible */
  import * as d3 from "d3"

  let data = [1000, 1500, 2000, 2500, 3000, 3500, 4000, 4500, 5000, 6000]

  let altura = d3
    .scaleLinear()
    .domain([0, d3.max(data)])
    .range([0, 400])

  let colorLightness = d3
    .scaleLinear()
    .domain([0, d3.max(data)])
    .range(["#eecc77", "#270D0B"])
</script>

<h2>Las galletitas que cociné ayer</h2>
<div class="container_2">
  {#each data as num}
    <div class="item_wrapper">
      <div class="circle" style="background-color: {colorLightness(num)}"></div>
    </div>
  {/each}
</div>
<p class="aclaracion">(Algunas se quemaron)</p>

<!-- Estilos CSS -->
<style>
  /* Estilos CSS */
  .container,
  .container_2 {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    height: 450px;
    /*border: 1px solid #000;*/
  }
  .container_2 {
    height: auto;
  }

  .aclaracion{
    text-align: center;
    margin-top: 20px;
  }

  .item_wrapper {
    display: flex;
    flex-direction: column;
    justify-content: end;
    align-items: center;
    gap: 10px;
  }
  .column {
    width: 80px;
    height: 100%;
    background-color: #ee0001;
  }

  h2{
    text-align: center;
  }
  .num {
    font-size: 21px;
    font-weight: bold;
    margin: 0;
    color: black;
  }
  .num_2 {
    font-size: 18px;
    margin: 0;
    color: black;
  }
  .circle {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background-color: #ee0001;
    border: 1px solid black;
  }
</style>
