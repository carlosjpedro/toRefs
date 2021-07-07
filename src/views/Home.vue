<template>
  <div>
    <label>Input in Parent</label>
    <input type="text" v-model="message"/>
    <Child v-model="message"/>
  </div>
</template>

<script lang="ts">
import {defineComponent, ref, watch} from 'vue';
import Child from "@/components/Child.vue";

export default defineComponent({
  name: 'Home',
  components: {
    Child,
  },
  setup() {
    const message = ref("Original Text");
    watch(message, (v) => console.log("ParentView message", v))
    return {message};
  }
});
</script>
