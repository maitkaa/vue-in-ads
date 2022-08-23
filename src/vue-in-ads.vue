<template>
  <div id="InAdsContainer"></div>
</template>

<script setup>
import {loadScript} from "vue-plugin-load-script";
import {defineProps, onMounted, ref, defineEmits} from 'vue';

const props = defineProps({
  config: {
    type: Object,
    default: {
      "container": "InAdsContainer",
      "mode": "1",
      "nocss": false,
      "lang": "et",
      "appartment": 2,
      "ihist": "1993",
      "defaultBaseLayer": "ALUSKAART",
      "baseLayers": ["ALUSKAART", "ORTOFOTO", "HYBRIID"],
      "mapLayers": ["AADRESS", "KATASTRIYKSUS"],
      "WMS": []
    }
  },
  location: {
    type: Object,
    default: {},
    required: true
  }
});
const emit = defineEmits(['update:locationValue'])
const script = "https://inaadress.maaamet.ee/inaadress/js/inaadress.min.js";
onMounted(() => {
  delete props.config.container;
  props.config.container = 'InAdsContainer';
  loadScript(script)
      .then(() => {
        console.info("Loaded:" + script);
        return new InAadress(props.config);
      })
      .catch(() => {
        console.error("Failed to load:" + script);
      });
  document.addEventListener('addressSelected', function (e) {
    props.location.value = e.detail;
    emit('update:locationValue', e.detail);
  });
});
</script>