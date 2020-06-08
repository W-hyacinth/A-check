<template>
  <div class="calender">
    <Date v-for="n in maxDate" :key="n" v-html="n" />
  </div>
</template>
<script>
import Date from '../components/Date.vue';

export default {
  name: 'Calender',
  components: {
    Date,
  },
  data() {
    return {
      maxDate: 20,
    };
  },
};
</script>
<style lang="scss" scoped>
  .calender {
    &:before,
    &:after {
      clear: both;
      display: block;
      content: '';
    }
    .date {
      float: left;
    }
  }
</style>
