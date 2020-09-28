<template>
  <div class=graph>
    <span id="view_time"></span>
    <chart></chart>
    <div class="btn"><router-link to="/form">体温入力</router-link></div>
  </div>
</template>

<script>
import Chart from './Chart';

export default {
  components: {
    Chart,
  },
}
</script>

<style>
.graph{
  margin: 50px 0 0 0;
}
</style>