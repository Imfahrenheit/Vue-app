<template>
<div class="well well-md text-center">
  <h3> Train of The day </h3>

  <ul class="list-group">
    <li class="list-group-item list-group-item-success"><strong> ABOUT TRAIN </strong> <br> {{information.journeySections[0].beginTimeTableRow.stationShortCode}} to {{information.journeySections[0].endTimeTableRow.stationShortCode}} - {{information.journeySections[0].locomotives[0].locomotiveType}} {{information.journeySections[0].locomotives[0].powerType}}
    </li>
    <li class="list-group-item list-group-item-info"><strong> WAGONS </strong><br> {{information.journeySections[0].wagons[0].wagonType}}, {{information.journeySections[0].wagons[1].wagonType}}, {{information.journeySections[0].wagons[2].wagonType}}, {{information.journeySections[0].wagons[3].wagonType}},
      {{information.journeySections[0].wagons[4].wagonType}}, {{information.journeySections[0].wagons[5].wagonType}}
    </li>
    <li class="list-group-item list-group-item-warning"><strong> MAX SPEED </strong><br> {{information.journeySections[0].maximumSpeed}}
    </li>
    <li class="list-group-item list-group-item-danger"><strong> Traing Length </strong><br> {{information.journeySections[0].totalLength}}
    </li>
  </ul>

</div>
</template>

<script>
export default {

  props: ['source', 'sourceChanged'],
  data() {
    return {


      information: [],
      date: ""
    }
  },
  methods: {
    updateSource: function(source) {


      let utc = new Date().toJSON().slice(0, 10).replace(/-/g, '-');
      this.date = utc;


      this.$http.get('https://rata.digitraffic.fi/api/v1/compositions/1?departure_date=' + this.date)
        .then(response => {
          this.information = response.data;





        });

    },

  },

  mounted: function() {
    this.updateSource(this.source);


  },
  watch: {
    source: function(val) {
      this.updateSource(val);



    }
  }
}
</script>
<style scoped>
.well {
  max-width: 400px;
  margin: 0 auto;
}
</style>
