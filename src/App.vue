<template>
  <div id="app" class="app">
    {{attacker}}
    <h1>The Civulator Returns</h1>
    <unit
      v-on:change="updateAttacker"
      role="attacker"
    >
    </unit>
  </div>
</template>

<script>
import Unit from './components/Unit.vue';
export default {
  name: 'app',
  components: {
    Unit,
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
  methods: {
    updateAttacker (payload) {
      this.$data.attacker = payload;
    }
  },
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
