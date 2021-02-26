<template>
  <label class="mb-2" for="number">
    <slot name="name"></slot>
  </label>
  <input class="green text-gray-700 border rounded-md mb-4 p-1 focus:outline-none focus:ring-green-500 focus:border-green-500" required id="number"
         :placeholder='placeholder' :type="type" :value="value"
         @input="$emit('writeInfo', $event.target.value)">
</template>

<script>
  export default {
    name: "MessengerLinksInput",
    emits: [ 'writeInfo' ],
    props: [ 'placeholder', 'value', 'type' ]
  }
</script>

<style scoped>
  .green {
    background: #e9fff3
  }
</style>