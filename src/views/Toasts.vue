<template>
  <div class="container mt-5">
    <b-button @click="showToast">Show Toast with custom content</b-button>

    <div class="text-center my-3">
      <b-button v-b-tooltip.hover title="Tooltip directive content">
        Hover Me
      </b-button>

      <b-button id="tooltip-target-1"> Hover Me </b-button>
      <b-tooltip target="tooltip-target-1" triggers="hover">
        I am tooltip <b>component</b> content!
      </b-tooltip>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    showToast() {
      // Use a shorter name for this.$createElement
      const h = this.$createElement;
      // Increment the toast count
      this.count++;
      // Create the message
      const vNodesMsg = h("p", { class: ["text-center", "mb-0"] }, [
        h("b-spinner", { props: { type: "grow", small: true } }),
        " Flashy ",
        h("strong", "toast"),
        ` message #${this.count} `,
        h("b-spinner", { props: { type: "border", small: true } }),
      ]);
      // Create the title
      const vNodesTitle = h(
        "div",
        { class: ["d-flex", "flex-grow-1", "align-items-baseline", "mr-2"] },
        [
          h("strong", { class: "mr-2" }, "The Title"),
          h("small", { class: "ml-auto text-italics" }, "5 minutes ago"),
        ]
      );
      // Pass the VNodes as an array for message and title
      this.$bvToast.toast([vNodesMsg], {
        title: [vNodesTitle],
        solid: true,
        variant: "info",
      });
    },
  },
};
</script>
