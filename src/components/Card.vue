<template>
  <div class="card">
    <img
      class="card-img"
      :src="`https://picsum.photos/300/200?random=${imageId}`"
      alt="image"
    />
    <span class="card-subtitle">{{ title }}</span>
    <div class="card-info">
      <span class="eth">{{ ethValue }} ETH</span><span class="bid">Bid</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imageId: { type: Number, default: 1 },
    title: String,
    ethValue: { type: Number, default: 4.0 },
  },
};
</script>