<template>


<div v-for="country in countries" :key="country">


 
   
   <div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        <p> {{country.name.official}} </p>
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
      <div class="accordion-body">
         <p> {{country.maps.googleMaps}} </p>
      </div>
    </div>
  </div>
</div>


</div>

</template>

<script>
export default {
   data(){
      return {
         countries: []
      }
   },
   mounted() {
      fetch('https://restcountries.com/v3.1/all')
         .then(res => res.json() )
         .then(data => this.countries = data )
   },
   methods(){
      
   }
}
</script>

<style>
.accordion{
   margin-left: 180px;
   margin-right: 180px;
}
</style>
