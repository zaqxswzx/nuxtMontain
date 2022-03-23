<script>
export default {
  props: ["theType"],
  data() {
    return {
      inInput: null,
    };
  },
};
</script>

<template>
  <div>
    <div v-if="theType !== 'select'">
      <input :type="theType" v-model="inInput" />
      {{ this.inInput }}
    </div>
    <select v-if="theType === 'select'" name="" id="">
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
    </select>
  </div>
</template>

<style>
</style>