## Vue In-Ads component

Simple component to load In-Ads map. Use the official documentation to get further information about all available fields and options.

The component creates a container with an `id="InAdsContainer"`, the   `container` field in the config will be omitted and **always overwritten.**
Also the component is initialized with default config, so it will work out of the box.

[![Image from Gyazo](https://i.gyazo.com/4e04f21cc7923ad63959ea61d2d0d2c5.gif)](https://gyazo.com/4e04f21cc7923ad63959ea61d2d0d2c5)
### Npm package link
[https://www.npmjs.com/package/vue-in-ads-component](https://www.npmjs.com/package/vue-in-ads-component)


### Info about In-Ads map(🇪🇪)

[https://inaadress.maaamet.ee/inaadress/](https://inaadress.maaamet.ee/inaadress/)

### Official documentation for In-Ads (🇪🇪)

[https://inaadress.maaamet.ee/inaadress/pdf/et/in_aadress_developer_manual.pdf](https://inaadress.maaamet.ee/inaadress/pdf/et/in_aadress_developer_manual.pdf)

---
## Install

```bash
npm i vue-in-ads-component
```

## Example of usage

```javascript
<script>
 import { defineComponent } from 'vue';
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
```
## Default config

```json
{
  "container": "InAdsContainer",
  "mode": "1",
  "nocss": false,
  "lang": "et",
  "appartment": 2,
  "ihist": "1993",
  "defaultBaseLayer": "ALUSKAART",
  "baseLayers": [
    "ALUSKAART",
    "ORTOFOTO",
    "HYBRIID"
  ],
  "mapLayers": [
    "AADRESS",
    "KATASTRIYKSUS"
  ],
  "WMS": []
}
```
