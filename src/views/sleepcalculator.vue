<template>
  <div class="container">
  <div class="row">
    <div class="col"><h3 id="Naslov1">When do you want to wake up?</h3></div>

    <div class="col"></div>
    <div class="col"><h3 id="Naslov1">When do you want to go to sleep?</h3></div>
  </div>
    <div id='row2' class="row">
         <div class="col"><div>
         <input type="number" min="0" max="23" placeholder="23" >:
         <input type="number" min="0" max="59" placeholder="00" >
         </div>
         </div>
         <div class="col"></div>
         <div class="col"><div>
         <input type="number" min="0" max="23" placeholder="8" v-model="variables.wakeuphours">:
         <input type="number" min="0" max="59" placeholder="00" v-model="variables.wakeupmins">
         </div></div>
    </div>
      <div id='row3' class="row">
         <div class="col"><router-link to="bedtime" ><button class="btn btn-primary" type="button">Calculate bedtime</button></router-link></div>
         <div class="col"><samp>a</samp></div>
         <div class="col"><router-link to="wakeuptime" v-on:click.native="wake_up_time_calculation()"><button class="btn btn-primary" type="button">Calculate wake-up time</button></router-link></div>
         
      </div>
</div>
</template>

<script>
import variables from "@/variables";

export default {
    name:"sleepcalculator",
    

methods: {
  wake_up_time_calculation(){
    let pomvar=variables.wakeupmins+360;
    variables.interval1_hours=variables.wakeuphours+(variables.minutes/60)
    variables.interval1_mins=pomvar%60

  }
}
 }
</script>
<style scoped>
#Naslov1{
  color: aliceblue;
}
#row2{
  margin-top:4%;
  
}
#row3{
  margin-top:4%;
}
</style>