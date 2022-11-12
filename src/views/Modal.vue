<template>
  <div class="container mt-5">
    <!-- <label for="example-datepicker">Choose a date</label>
    <b-form-datepicker
      id="example-datepicker"
      v-model="value"
      class="mb-2"
    ></b-form-datepicker>
    <p>Value: '{{ value }}'</p> -->
    <div>
      <b-button v-b-modal.modal-1>Show Modal</b-button>
      <b-modal id="modal-1" title="Vue Js Bootstrap Modal Example">
        <p class="my-4">Content goes here...</p>
      </b-modal>
    </div>
    <br />
    <blockquote class="blockquote text-right">
      <p class="mb-1">A well-known quote, contained in a blockquote element.</p>
      <footer class="blockquote-footer">
        Someone famous in <cite title="Source Title">Source Title</cite>
      </footer>
    </blockquote>

    <!--  -->

    <br />
    <hr />

    <!-- Calendar -->
    <b-row>
      <b-col md="auto">
        <b-calendar
          v-model="value"
          @context="onContext"
          locale="pt-BR"
          :date-disabled-fn="dateDisabled"
          :date-info-fn="dateClass"
          :min="min"
          :max="max"
        ></b-calendar>
      </b-col>
      <b-col>
        <p>
          Value: <b>'{{ value }}'</b>
        </p>
        <p class="mb-0">Context:</p>
        <pre class="small">{{ context }}</pre>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
  data() {
    const now = new Date();
    const today = new Date(now.getFullYear(), now.getMonth(), now.getDate());
    // 15th two months prior
    const minDate = new Date(today);
    minDate.setMonth(minDate.getMonth());
    minDate.setDate(15);
    // 15th in two months
    const maxDate = new Date(today);
    maxDate.setMonth(maxDate.getMonth() + 2);
    maxDate.setDate(15);
    return {
      value: "",
      context: null,
      dia: 8,
      mes: 11,
      datasFolga: [
        "2022-11-08",
        "2022-11-09",
        "2022-11-10",
        "2022-05-26",
        "2022-07-05",
        "2022-09-19",
        "2022-02-03",
        "2022-05-02",
      ],
      min: minDate,
      max: maxDate,
    };
  },
  methods: {
    dateDisabled(ymd, date) {
      // Disable weekends (Sunday = `0`, Saturday = `6`) and
      // disable days that fall on the 13th of the month
      const weekday = date.getDay();
      const day = date.getDate();
      const month = date.getMonth();
      // Return `true` if the date should be disabled
      // return weekday === 0 || weekday === 6 || day === 13;

      const d = new Date(date.getFullYear(), month, day);
      const datasFolgaString = this.datasFolga.map((el) =>
        new Date(
          el.split("-")[0],
          el.split("-")[1] - 1,
          el.split("-")[2]
        ).getTime()
      );
      if (datasFolgaString.includes(d.getTime()) || weekday == 0) {
        return true;
      } else {
        return false;
      }
    },
    dateClass(ymd, date) {
      const day = date.getDate();
      return day >= 10 && day <= 20 ? "table-info" : "";
    },
    onContext(ctx) {
      this.context = ctx;
    },
  },
};
</script>
