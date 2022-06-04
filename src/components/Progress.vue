<template>
  <div style="width:350px; margin:0 auto 36px">
    <h3 style="text-align:center; margin-bottom:20px">
      <h4>대회 진행률</h4>
      <span style="color:#212121;">{{ sum }}</span>
      <span style="color:#757575;"> / 100%</span>
    </h3>
    <v-progress-linear
      :buffer-value="sum"
      :value="sum"
      stream
      color="orange"
    ></v-progress-linear>
  </div>
</template>

<script>
export default {
  props: ["sum"],
};
</script>
