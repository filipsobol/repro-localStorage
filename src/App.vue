<template>
  <div>
    <p>State: {{ state }}</p>
    
    <div>
      <button @click="setState">Set state</button>
    </div>

    <div>
      <button @click="clearLocalStorage">Clear local storage</button>
    </div>
  </div>
</template>

<script>
import { useStorage } from "@vueuse/core";

export default {
  setup() {
    const state = useStorage("state", null, localStorage);

    function setState() {
      state.value = "IS SET";
    }

    function clearLocalStorage() {
      localStorage.clear();
    }

    return {
      state,
      setState,
      clearLocalStorage
    };
  }
}
</script>
