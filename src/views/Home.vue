<template>
  <div>
    <input type="text" v-model="message"/>
    <Child :msg="message"/>
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
    watch(message, (v) => console.log("Parent view message", v))
    return {message};
  }
});
</script>
