<template>
  <div class="result">
    <div class="title">You got {{ result }} / 15 correct!</div>
    <div class="desc">
      {{ result < 10 ? results[0].desc : results[1].desc }}
    </div>
  </div>
</template>

<script>
export default {
  name: "ResultComponent",
  props: ["results", "result"],
};
</script>
