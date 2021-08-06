<template>
  <div>
    <h1>Geolocation</h1>
    <p>Your location is:</p>
    <p>Latitude: {{ loc.lat }}</p>
    <p>Longitude: {{ loc.long }}</p>

    <button @click="getCurrentPosition">
      Get Current Location
    </button>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';
import { Geolocation } from '@capacitor/geolocation';

export default {
  name: 'ExploreContainer',
  props: {
    name: String
  },
  setup() {
    const loc = ref<{
      lat: null | number;
      long: null | number;
    }>({
      lat: null,
      long: null,
    });

    const getCurrentPosition = async () => {
      const pos = await Geolocation.getCurrentPosition();
      loc.value = {
        lat: pos.coords.latitude,
        long: pos.coords.longitude,
      };
    };
    return { getCurrentPosition, loc };
  },
}
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>