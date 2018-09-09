<template>
  <div>
    <label
      :for=selectorId
    >
      {{label}}: 
    </label>
    <select
      :id=selectorId
      v-on:change="e => $emit('change', e.target.value)"
    >
      <option
        v-for="option in options"
        v-bind:key=option
      >
        {{option}}
      </option>
    </select>
  </div>
</template>

<script>
  export default {
    name: 'selector',
    props: {
      options:{
        type: Array,
        required: true,
      },
      label: String,
    },
    computed: {
      selectorId: function () {
        return `selector-${this.label}`.toLowerCase()
      }
    }
  };
</script>

<style>
</style>
