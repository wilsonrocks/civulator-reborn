<template>
  <div class="unit-selector">
    {{role}}
    <selector
      :options=unitNames
      v-on:change="unitChange" 
      label="Unit"
    />
    <selector
      :options=levelNames
      v-on:change="levelChange"
      label="Level"
    />
  </div>
</template>

<script>

import {units, levels} from '../constants';
import Selector from './Selector.vue';
export default {
  name: 'unit',
  components: {
    Selector
    },
  data: () => ({
    unit: 'warriors',
    level: 'green',
  }),
  computed: {
    units: () => units,
    unitNames: () => units.map(unit => unit.name),
    levels: () => levels,
    levelNames: () => levels.map(level => level.name),
  },
  methods: {
    unitChange(newUnit) {
      this.unit = newUnit;
      this.$emit('change', this.$data);
    },
    levelChange(newLevel) {
      this.level = newLevel;
      this.$emit('change', this.$data);
    }
  },
  props: {
    role: String,
  }

}
  
</script>


<style>
  .unit-selector {
    border: 1px solid black;
  }
</style>
