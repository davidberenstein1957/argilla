<template>
  <SimilarityConfigDropdown v-model="selected" :options="['most', 'least']" />
</template>
<script>
export default {
  props: {
    value: {
      type: String,
      required: true,
    },
  },
  model: {
    prop: "value",
    event: "onValueChanged",
  },
  data() {
    return {
      selected: this.value,
    };
  },
  watch: {
    selected() {
      this.$emit("onValueChanged", this.selected);
    },
  },
};
</script>
