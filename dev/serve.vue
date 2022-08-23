<script>
import {defineComponent} from 'vue';
import VueInAds from '@/vue-in-ads.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    VueInAds
  },
  data: () => ({
    config: {
      "container": "InAdsContainer",
      "mode": "1",
      "nocss": false,
      "lang": "et",
      "appartment": 2,
      "ihist": "1993",
      "defaultBaseLayer": "ORTOFOTO",
      "baseLayers": ["ORTOFOTO"],
      "mapLayers": ["AADRESS", "KATASTRIYKSUS"],
      "WMS": []
    },
    location: {}
  })
});
</script>

<template>
  <div id="app">
    <vue-in-ads :config="config" :location="location"/>
    <h2>Chosen Location:</h2>
    <pre>
      {{ location }}
    </pre>
  </div>
</template>
