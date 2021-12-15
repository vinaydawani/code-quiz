<template>
  <div class="grid grid-flow-row grid-cols-3 gap-x-7 gap-y-10 p-4">
    <div
      class="flex place-content-center"
      v-for="photo in data"
      :key="photo.id"
    >
      <img :src="photo.path" alt="" class="" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["data"],
};
</script>
