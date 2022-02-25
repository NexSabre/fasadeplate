<template>
  <q-page class="row items-center full-width">
    <div class="items-center">
      <q-card class="full-width">
        <h2>Diagonal</h2>
        <br />
        <div>
          <q-input v-model="short" type="number">Short</q-input>
          <q-input v-model="long" type="number">Long</q-input>

          <q-select filled v-model="model" :options="options" label="Filled" />
        </div>
        <q-card-section>
          <h5>Results: {{ calculate }} {{ text }}</h5>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "Diagonal",
  data() {
    return {
      model: ref("cm"),
      short: 0,
      long: 0,
      options: ["mm", "cm", "dm", "m"],
      text: ref("cm"),
    };
  },

  computed: {
    calculate(): number {
      const preciseResult: number = Math.sqrt(
        Math.pow(this.short, 2) + Math.pow(this.long, 2)
      );
      return Math.round((preciseResult + Number.EPSILON) * 100) / 100;
    },
  },

  watch: {
    model: function () {
      this.text = this.model ? this.model : ref("cm").toString();
    },
  },
});
</script>
