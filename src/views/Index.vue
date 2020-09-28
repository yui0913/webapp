<template>
  <div>
    <span id="view_time"></span>
    <chart></chart>
    <router-link to="/form">体温入力</router-link>
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

