<template>
  <select @change="emitValue" v-model="valueOption">
    <option value="">Select {{ labelKey }}</option>
    <option v-for="i in getUniqueNameKey" :key="i" :value="i">{{ i }}</option>
  </select>
</template>

<script>
export default {
  name: "SelectComponent",
  props: {
    labelKey: String,
    cds: Array,
  },
  data() {
    return {
      valueOption : "",
    }
  },
  methods: {
    emitValue() {
      this.$emit("change-value", this.valueOption, this.labelKey)
    }
  },
  computed: {
    getNameKey() {
      return this.cds.map((cd)=> {
        return cd[this.labelKey];
      })
    },
    getUniqueNameKey() {
      const myArray = [];
      this.getNameKey.forEach((item)=> {
        if (!myArray.includes(item)) {
          myArray.push(item);
        }
      })
      return myArray
    }
  }
}
</script>

<style>

</style>