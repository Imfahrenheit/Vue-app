<template >
<div v-if="show" class="container-fluid">


  <div class="grid">
    <div class="box">
      <h3> S967 HKI-TKU</h3>
      <!-- Locomotive type and power type -->
      <ul>
        <li> <span class=" glyphicon glyphicon-asterisk"></span>Locomotive: SM3 Electric </li>
        <!-- Wagon types and theirs total length-->
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: CM, IM, TTC, IM1 (99 meters)</li>
        <!-- Train max speed -->
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 200KM/h </li>
      </ul>
    </div>

    <div class="box">
      <h3>	IC962 TKU-HKI </h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>spLocomotive: SR2 Electric </li>
        <li><span class="glyphicon glyphicon-asterisk"></span> Wagons: Edo, Edb, ERd, Ed (126 meters) </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>

    <div class="box">
      <h3>	IC972 TUS-HKI</h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: SR2 Electric </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: Edo, Edb, ERd, Eds (126 meters) </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>

    <div class="box">
      <h3>	IC945 HKI-TKU</h3>
      <ul>
        <li><span class="glyphicon glyphicon-asterisk"></span>Locomotive: SR2 Electric </li>
        <li><span class="glyphicon glyphicon-asterisk"></span>Wagons: Edfs, Edb, Edo (99 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>

    <div class="box">
      <h3> IC948 TUS-HKI </h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: Sr2 Electric </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: Edo, Edb, ERd, Eds, Ed (152 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>

    <div class="box">
      <h3> IC951 HKI-TKU </h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: Sr2 Electric </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: Edo, Edb, ERd, Eds (126 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>

    <div class="box">
      <h3>	IC954 TKU-HKI</h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: Sr2 Electric </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: Edo, Edb, Edfs (99 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>
    <div class="box">
      <h3>	IC955 HKI-TKU </h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: Sr2 Electric </li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: Edo, Edb, Edfs (99 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>
    <div class="box">
      <h3>	IC958 TKU-HKI </h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: SM3 Electric</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: IM1, CMH, TTC, TT, CM, IM2 (160 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 200KM/h </li>
      </ul>
    </div>
    <div class="box">
      <h3>	IC960 TKU-HKI </h3>
      <ul>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Locomotive: Sr2 Electric</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Wagons: Edo, Edb, Edfs, Ed (126 meters)</li>
        <li> <span class="glyphicon glyphicon-asterisk"></span>Max speed: 160KM/h </li>
      </ul>
    </div>
  </div>
  <div>

    <div class="container well well-md text-center">
      <button v-on:click="show = !show" class="btn btn-success btn-md">
    <span class="glyphicon glyphicon-arrow-up"></span> HIDE THE STATIC CONTENT
    <span class="glyphicon glyphicon-arrow-up"></span>
  </button>
    </div>


  </div>


</div>
</template>

<script>
export default {
  data() {
    return {
      show: true,

    }
  },
  methods: {

  }
}
</script>

<style >
.grid {


  padding-top: 20px;
  height: auto;
  padding: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-content: space-between;
  flex-wrap: wrap;
}

.box {
  border-radius: 15px;
  box-shadow: 10px 10px 5px #a5a9b2;
  display: block;
  background-color: red;
  margin: 2.5px auto 10px;
  width: 220px;
  height: 220px;
  background-color: #F5F5F5;
}

.box h3 {
  text-align: center;
  color: #f4979f;
}

.box ul li {

  list-style: none;
  padding: 3px;
}

.btn:focus {
  outline: none;
}
</style>
