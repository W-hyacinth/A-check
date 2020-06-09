<template>
  <a class="date" href="#">

  </a>
</template>
<script>
export default {
  name: 'Date',
};
</script>
<style lang="scss" scoped>
  .date {
    width: 40px;
    height: 40px;
    font-size: 14px;
    color: #000;
    text-align: center;
    line-height: 40px;
    border: 1px solid #000;
    border-radius: 50%;
    box-sizing: border-box;
    &.attend {
      background-color: #0bf;
    }
  }
</style>
