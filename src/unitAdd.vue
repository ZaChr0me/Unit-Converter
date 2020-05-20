<template>

  <form   @submit.prevent="add()">
    <div>
    <label>Conversion Unit</label>
    <input type="text" v-model="Units.type">
    </div>
    <div>
    <label>Conversion Rate</label>
    <input type="text" v-model.number="Units.rate">
    <button>Add the unit</button>
    </div>
  </form>

</template>
<script>
export default {
  data() {
      return {
        Units: {},
      };
    },
  methods: {
    add() {
       this.$emit('added', this.Units);
       this.Units = {};
    }
  }
}
</script>