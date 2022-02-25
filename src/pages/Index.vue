<template>
  <q-page class="row items-center">
    <div class="items-center">
      <h2>Diagonal</h2>
      <br />

      <q-numeric v-model="t" />
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  data() {
    return {
      t: 0,
    };
  },
});
</script>
