<template>
  <div>
    <div class="columns is-centered">
      <div class="column is-four-fifths">
        <vl-map :load-tiles-while-animating="true" :load-tiles-while-interacting="true"
                data-projection="EPSG:4326" style="height: 400px">
          <vl-view :zoom.sync="zoom" :center.sync="center" :rotation.sync="rotation"></vl-view>

          <vl-geoloc @update:position="geolocPosition = $event">
            <template slot-scope="geoloc">
              <vl-feature v-if="geoloc.position" id="position-feature">
                <vl-geom-point :coordinates="geoloc.position"></vl-geom-point>
                <vl-style-box>
                  <vl-style-icon src="_media/marker.png" :scale="0.4" :anchor="[0.5, 1]"></vl-style-icon>
                </vl-style-box>
              </vl-feature>
            </template>
          </vl-geoloc>

          <vl-layer-tile id="osm">
            <vl-source-osm></vl-source-osm>
          </vl-layer-tile>

          <vl-overlay id="overlay" :position="overlayCoordinate">
            <template slot-scope="scope">
              <div class="overlay-content">
                Phone Number<br>
                Address
              </div>
            </template>
          </vl-overlay>

        </vl-map>
      </div>
    </div>
    
    <div class="columns is-centered">
      <div class="column is-two-fifths form">
      <h1 class="form-title">Contact form</h1>
        <div class="field">
          <label class="label is-pulled-left">Name</label>
          <div class="control">
            <input class="input" type="text" placeholder="Text input">
          </div>
        </div>

        <div class="field">
          <label class="label is-pulled-left">Email</label>
          <div class="control">
            <input class="input" type="email" placeholder="Email input">

          </div>
        </div>

        <div class="field">
          <label class="label is-pulled-left">Message</label>
          <div class="control">
            <textarea class="textarea" placeholder="Text area"></textarea>
          </div>
        </div>

        <div class="field is-grouped">
          <div class="control">
            <button class="button is-link">Submit</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
  export default {
    name: 'contact',
    components: {
    },
    data () {
      return { 
        zoom: 14,
        center: [-73.56670039591228, 45.49822605451584],
        rotation: 0,
        geolocPosition: undefined,
        overlayCoordinate: [-73.56670039591228, 45.49822605451584]
      }
    },
  }
</script>

<style scoped>
  .overlay-content {
    padding: 20px;
    border-radius: 25px;
    background-color: white;
  }

  .form {
    margin: 25px 0px 50px 0px;
    padding: 25px;
    border: 2px solid #DBDBDB;
    border-radius: 5px;
  }

  .form-title {
    font-weight: bold;
  }
</style>