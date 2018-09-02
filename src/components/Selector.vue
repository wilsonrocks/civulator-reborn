<template>
  <select>
    <option
      v-for="option in options"
      v-bind:key=option
    >
      {{option}}
    </option>
  </select>

</template>

<script>
  export default {
    name: 'selector',
    props: {
      options:{
        type: Array,
        required: true,
      },
    }
  };
</script>

<style>
</style>
