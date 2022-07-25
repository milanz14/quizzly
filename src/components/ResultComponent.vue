<template>
  <div class="result">
    <div class="title">You got {{ result }} correct!</div>
    <div class="desc">{{ result < 3 ? results[0].desc : results[1].desc }}</div>
  </div>
</template>

<script>
export default {
  name: "ResultComponent",
  props: ["results", "result"],
};
</script>
