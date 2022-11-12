<template>
  <div class="container mt-5">
    <b-progress
      id="minhaBar"
      :value="valueMinhaBar[0]"
      variant="success"
      striped
      show-value
      :animated="animate"
    ></b-progress>
    <b-progress
      :value="valueMinhaBar[1]"
      variant="info"
      striped
      show-value
      :animated="animate"
      class="mt-2"
    ></b-progress>
    <b-progress
      :value="valueMinhaBar[2]"
      variant="warning"
      striped
      show-value
      :animated="animate"
      class="mt-2 w-50"
    ></b-progress>
    <b-progress
      :value="valueMinhaBar[3]"
      variant="danger"
      striped
      show-value
      :animated="animate"
      class="mt-2"
      height="2rem"
    ></b-progress>

    <b-button variant="secondary" @click="animate = !animate" class="mt-3">
      {{ animate ? "Stop" : "Start" }} Animation
    </b-button>
    <b-button @click="mudarValuesBars" class="mt-3 ml-3"
      >mudarValuesBars</b-button
    >
  </div>
</template>

<script>
export default {
  data() {
    // const bars = document.getElementsByTagName("b-progress");
    const bars = document.getElementById("minhaBar");
    return {
      animate: true,
      bars: bars,
      valueMinhaBar: [20, 30, 40, 50],
    };
  },
  methods: {
    mudarValuesBars() {
      window.setInterval(() => {
        this.valueMinhaBar = this.valueMinhaBar.map((valor) => {
          return parseInt(Math.random() * 100);
        });
        console.log(this.valueMinhaBar);
      }, 750);
    },
  },
};
</script>
