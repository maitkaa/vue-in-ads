## Vue In-Ads component

Simple component to load In-Ads map. Use the official documentation to get further information about all available fields and options.

The component creates a container with an `id="InAdsContainer"`, the   `container` field in the config will be omitted and **always overwritten.**

### Info about In-Ads map(🇪🇪)

[https://inaadress.maaamet.ee/inaadress/](https://inaadress.maaamet.ee/inaadress/)

### Official documentation for In-Ads (🇪🇪)

[https://inaadress.maaamet.ee/inaadress/pdf/et/in_aadress_developer_manual.pdf](https://inaadress.maaamet.ee/inaadress/pdf/et/in_aadress_developer_manual.pdf)

---

## Example of usage

```javascript
<script>
import { defineComponent } from 'vue';
import VueInAds from '@/vue-in-ads.vue';

export default defineComponent({
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
    }
  })
});
</script>

<template>
  <div id="app">
    <vue-in-ads :config="config" />
  </div>
</template>
```
