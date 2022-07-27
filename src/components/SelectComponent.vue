<template>
  <select v-model="valueOption">
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
  computed: {
    getFilteredArray() {
      return this.cds.filter((cd)=> {
        const currentTextKey = cd[this.labelKey];
        if (!this.valueOption) return true;
        else if(currentTextKey == this.valueOption) {
          return true;
        }
        else return false
      })
    },
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