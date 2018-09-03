<template>
  <div id="app">
    <h1>The Civulator Returns</h1>
    <selector
      :options=unitNames
      label="Attacker"
    />

    <selector
      :options=unitNames
      label="Defender"
    />
  </div>
</template>

<script>

import {units} from './constants';
import Selector from './components/Selector.vue';
export default {
  name: 'app',
  components: {
    Selector,
  },
  data: () => ({
    attacker: {
      unit: 'warriors',
      level: 'green',
    },
    defender: {
      unit: 'phalanx',
      level: 'veteran',
      fortified: true,
    },
    location: {
      terrain: 'grassland',
      city: true,
      walls: true,
      coastalDefence: false,
      samBattery: false,
      fortress: false,
    },
  }),
  computed: {
    units() {
      return units;
    },
    unitNames() {
      return units.map(unit => unit.name);
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
