<template>
  <div>
    <RightImgCard />
    <LeftImgCard />
  </div>
</template>

<script>
export default {
  middleware: ["auth"],
};
</script>
