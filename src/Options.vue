<template>
<div class="text-center">
  <div class="container-fluid well well-md text-center">

    <h3 class="text-info">
                  <div class="">
                    <span class="glyphicon glyphicon-list-alt"></span>
                  </div>
                  CHECK TRAINS
                </h3>
    <select class="form-control" v-on:change="sourceChanged">
                <option v-for="source in sources" v-bind:value="source.version">{{source.trainType}}{{source.trainNumber}}
                  {{source.timeTableRows[0].type}}-
                  {{source.timeTableRows[0].stationShortCode}}</option>

                </select>
  </div>
  <div v-if="ok" class="jumbotron">
    <strong> TRAIN DETAILS</strong>

    <div class="table-responsive">
      <table class="table table-bordered">
        <thead>
          <tr class="danger">
            <th>Number</th>
            <th>Date</th>
            <th>Departure station</th>
            <th> Currently moving</th>
            <th> Description</th>
          </tr>
        </thead>
        <tbody>
          <tr class="success">
            <td> {{source.trainType}}-{{source.trainNumber}}</td>
            <td>{{source.departureDate}}</td>
            <td>{{source.timeTableRows[0].stationShortCode}}</td>
            <td>{{source.runningCurrently}}</td>
            <td> {{source.trainCategory}} <br>{{source.timetableType}} </td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>

</div>

</div>
</template>

<script>
export default {



  data() {
    return {
      sources: [],
      source: '',
      ok: false
    }
  },
  methods: {
    sourceChanged: function(e) {
      for (var i = 0; i < this.sources.length; i++) {
        if (this.sources[i].version == e.target.value) {
          this.source = this.sources[i];
        }
      }
      return this.ok = true;
      this.$emit('sourceChanged', e.target.value);

    }

  },
  created: function() {
    this.$http.get('https://rata.digitraffic.fi/api/v1/live-trains')
      .then(response => {
        this.sources = response.data;


      })

  }
}
</script>

<style>
.form-control {
  max-width: 400px;
  margin: 0 auto;
}
</style>
