<script>
  import { Map, LngLatBounds, LngLat, addProtocol } from "maplibre-gl";
  import { Protocol } from "pmtiles";

  // import { cogProtocol } from "@geomatico/maplibre-cog-protocol";
  import "maplibre-gl/dist/maplibre-gl.css";
  import { onMount } from "svelte";

  // addProtocol("cog", cogProtocol);
  let protocol = new Protocol()
  addProtocol('pmtiles', protocol.tile);



  onMount(() => {
    const map = new Map({
      container: "map",
      style: {
        version: 8,
        sources: {
          "raster-tiles": {
            type: "raster",
            tiles: [
              "https://mt0.google.com/vt/lyrs=s&x={x}&y={y}&z={z}",
              "https://mt1.google.com/vt/lyrs=s&x={x}&y={y}&z={z}",
              "https://mt2.google.com/vt/lyrs=s&x={x}&y={y}&z={z}",
              "https://mt3.google.com/vt/lyrs=s&x={x}&y={y}&z={z}",
            ],
            tileSize: 256,
          },
        },
        layers: [
          { id: "raster-layer", type: "raster", source: "raster-tiles" },
        ],
      },
      center: [-120.6290359, 50.7412884],
      maxBounds: new LngLatBounds(
        new LngLat(-120.6, 50.6),
        new LngLat(-119.9, 50.9),
      ),
      zoom: 10,
    });

    map.on("load", () => {
      map.addSource("my-layer", {
        type: "raster",
        url: "http://localhost:8000/accepted_insolation.tif",
        tileSize: 256,
      });

      map.addLayer({
        id: "my-layer-layer",
        source: "my-layer",
        type: "raster",
      });
    });

    return () => map.remove();
  });
</script>

http

<section id="center">
  <div>
    <h1>Kamloops Rooftop Solar Resources</h1>
    <p>This tool is to let you explore and check out what we got!</p>
  </div>
</section>

<section id="next-steps">
  <div id="map"></div>
</section>