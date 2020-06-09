<template>
  <div class="calender">
    <Date v-for="n in maxDate" :key="n" :class="{'attend': attend[n] === 1}"
    @click="checkAttend(n)" v-html="n" ref="calender" />
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
      maxDate: 100,
      attend: [1, 0, 1, 1, 1, 1, 0, 1, 0, 1, 0],
      chance: 2,
    };
  },
  methods: {
    checkAttend(index, event) {
      /* eslint-disable */
      alert(index);
      if (this.attend[index] === 1) {
        console.warn('이미 이 날 출석했단다. 다른날을 눌러보렴');
      } else if (this.chance < 0) {
        console.error('어머나 이미 기회가 없구나. 연속 출석은 힘들겠어');
      } else {
        const addAttend = window.confirm('결석한 이 날을 출석으로 바꿔 줄까?');
        if (addAttend) {
          this.chance = 1;
          this.$refs.calender.classList.add('attend');
        }
      }
      console.log(index);
      event.preventDefault();
    },
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
