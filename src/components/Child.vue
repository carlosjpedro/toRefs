<template>
  <div>
    <label for="componentInput">Input in Child</label>
    <input id="componentInput" type="text" v-model="msg.stringValue"/>
    <br>
    <label for="componentSpan">Span in Child</label>
    <span id="componentSpan">{{ msg.stringValue }}</span>
  </div>
</template>

<script lang="ts">


import {defineComponent, toRefs} from 'vue';

export default defineComponent({
  props:
      ['modelValue'],
  setup(props) {
    const {modelValue: msg} = toRefs(props);

    return {msg,};
  }
});
</script>