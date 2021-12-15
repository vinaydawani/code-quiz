<template>
  <section class="h-screen flex flex-col">
    <div class="mt-4 text-center place-self-center">
      <span class="uppercase font-sora text-xl text-gray-700"
        >meet the team</span
      >
    </div>
    <div class="w-2/3 py-6 place-self-center">
      <gridComp :data="gridData"></gridComp>
    </div>
  </section>
</template>

<script>
import gridComp from "@/components/gridComp.vue";

export default {
  name: "App",
  components: { gridComp },
  setup() {
    const gridData = [];

    const importImage = (r) => {
      for (let i = 0; i < r.keys().length; i++) {
        gridData.push({
          id: i,
          path: r(r.keys()[i]),
        });
      }
    };

    importImage(require.context("./assets/images/grid/", true, /\.png$/));

    return { gridData };
  },
};
</script>

<style>
body {
  height: 100%;
}

span {
  letter-spacing: 0.2em !important;
}

span::after {
  content: "";
  display: inline-block;
  background-color: black;
  width: 25vw;
  height: 1px;
  margin-left: 1.5rem;
  vertical-align: middle;
}

span::before {
  content: "";
  display: inline-block;
  background-color: black;
  width: 25vw;
  height: 1px;
  margin-right: 1.5rem;
  vertical-align: middle;
}
</style>
