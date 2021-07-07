<template>
  <div>
    <label for="componentInput">Input in Child</label>
    <input id="componentInput" type="text" :value="msg" @input="handler($event.target.value)"/>
    <br>
    <label for="componentSpan">Span in Child</label>
    <span id="componentSpan">{{ msg }}</span>
  </div>
</template>

<script lang="ts">


import {defineComponent, toRefs} from 'vue';

export default defineComponent({
  props: {
    modelValue: {
      type: String,
      required: true
    },
  },
  emits: [
    'update:modelValue'
  ],
  setup(props) {
    const {modelValue: msg} = toRefs(props);
    
    const handler = (v:string) =>  msg.value = v;
    return {msg, handler};
  }
});
</script>