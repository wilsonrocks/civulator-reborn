<template>
  <div id="app">
    <h1>The Civulator Returns</h1>
    <fieldset>
    <selector
      :options=unitNames
      label="Attacker"
    />
    <selector
      :options=levelNames
      label="Level"
    />
    </fieldset>

    <fieldset>
      <selector
        :options=unitNames
        label="Defender"
      />
      <selector
        :options=levelNames
        label="Level"
      />
    </fieldset>

  </div>
</template>

<script>
import {units, levels} from './constants';
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
    units: () => units,
    unitNames: () => units.map(unit => unit.name),
    levels: () => levels,
    levelNames: () => levels.map(level => level.name),
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
