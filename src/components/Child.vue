<template>
  <div>
    <label for="componentInput">Input in Component</label>
    <input id="componentInput" type="text" v-model="watchedMsg"/> 
    <br>
    <label for="componentSpan"></label> <span id="componentSpan">{{ watchedMsg }}</span>
  </div>
</template>

<script lang="ts">
import {defineComponent, toRefs, watch} from 'vue';

export default defineComponent({
  props: {
    msg: {
      type: String,
      required: true
    },
  },
  setup(props) {
    const {msg: watchedMsg} = toRefs(props);

    //watch(watchedMsg, (v)=> console.log(`New message value ${watchedMsg}`))

    return {watchedMsg};

  }
});
</script>