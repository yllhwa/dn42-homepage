<script setup lang="ts">
import { useData } from 'vitepress'

// https://vitepress.dev/reference/runtime-api#usedata
const { site, frontmatter } = useData()
import { onMounted } from 'vue';

const WH = [114.298572, 30.584355];
const NJ = [105.066138, 29.58708];
const BJ = [116.407526, 39.90403];
const HK = [114.177314, 22.266416];
const FR = [2.3522219, 48.856614];
const KR = [127.73, 37.8185];

const locations: { name: string, location: any }[] = [
  { name: 'Wuhan', location: WH },
  { name: 'Hong Kong', location: HK },
  { name: 'Neijiang', location: NJ },
  { name: 'Paris', location: FR },
  { name: 'Seoul', location: KR },
  { name: 'Beijing', location: BJ },
];

import 'leaflet/dist/leaflet.css';

onMounted(() => {
  // import L from "leaflet";
  import("leaflet").then((L) => {
    var map = L.map('map', { attributionControl: false }).setView([51.505, -0.09], 13);
    L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);
    locations.forEach((location) => {
      L.marker(location.location.reverse()).addTo(map)
        .bindPopup(location.name);
    });
    map.setView([35.86166, 104.195397], 3);
  });
});
</script>

<template>
  <div id="map"></div>
</template>

<style>
#map {
  width: 100%;
  height: 500px;
}
</style>
