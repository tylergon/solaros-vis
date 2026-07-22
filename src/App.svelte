<script lang="ts">
  // import './app.css'
  import type * as maplibregl from 'maplibre-gl';
  import {
    MapLibre,
    NavigationControl,
    ScaleControl
  } from 'svelte-maplibre-gl'
  import { PMTilesProtocol } from '@svelte-maplibre-gl/pmtiles';

  

  // // import { cogProtocol } from "@geomatico/maplibre-cog-protocol";
  // import "maplibre-gl/dist/maplibre-gl.css";




</script>

<!-- <PMTilesProtocol /> -->

<section id="center">
  <div>
    <h1>Kamloops Rooftop Solar Resources</h1>
    <p>This tool is to let you explore and check out what we got!</p>
  </div>
</section>

<section id="map">
  <MapLibre
      class="h-[55vh] min-h-75"
      style="https://basemaps.cartocdn.com/gl/voyager-gl-style/style.json"
      zoom={3.5}
      center={{ lng: 137, lat: 36 }}
  >
    <NavigationControl />
    <ScaleControl />
  </MapLibre>
</section>