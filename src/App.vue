<template>
  <section class="h-screen flex flex-col">
    <div class="text-center">
      <span class="uppercase font-sora">meet the team</span>
    </div>
    <div class="w-2/3 place-self-center">
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
    // const gridData = [
    //   "./assets/images/grid/1.png",
    //   "./assets/images/grid/2.png",
    //   "./assets/images/grid/1.png",
    //   "./assets/images/grid/2.png",
    //   "./assets/images/grid/1.png",
    //   "./assets/images/grid/2.png",
    // ];

    const importImage = (r) => {
      // r.keys().forEach((key) => {
      //   gridData.push({
      //     id: 1,
      //     path: r(key),
      //   });
      // });
      for (let i = 0; i < r.keys().length; i++) {
        gridData.push({
          id: i,
          path: r(r.keys()[i]),
        });
      }
    };

    const gridData = [
      // {
      //   id: 1,
      //   path: require("./assets/images/grid/1.png"),
      // },
      // {
      //   id: 2,
      //   path: require("./assets/images/grid/1.png"),
      // },
      // {
      //   id: 3,
      //   path: require("./assets/images/grid/1.png"),
      // },
      // {
      //   id: 4,
      //   path: require("./assets/images/grid/1.png"),
      // },
      // {
      //   id: 5,
      //   path: require("./assets/images/grid/1.png"),
      // },
      // {
      //   id: 6,
      //   path: require("./assets/images/grid/1.png"),
      // },
    ];

    importImage(require.context("./assets/images/grid/", true, /\.png$/));
    console.log(gridData);

    return { gridData };
  },
};
</script>

<style>
body {
  height: 100%;
}
</style>
