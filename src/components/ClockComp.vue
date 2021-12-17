<template>
  <div class="clockClass" id="clock">
    <h1 v-for="item in mainArray" :key="item.id" :id="item.id">
      {{ item.value }}
    </h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      days: [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ],
      mainArray: [
        { id: "A", value: "" },
        { id: "B", value: "" },
        { id: "C", value: "" },
        { id: "D", value: "" },
        { id: "E", value: "" },
        { id: "F", value: "" },
        { id: "G", value: "" },
      ],
    };
  },
  created: function () {
    setInterval(() => {
      let currDate = new Date();
      let hours;
      if (currDate.getHours() < 10) {
        hours = "0" + currDate.getHours();
      } else {
        hours = currDate.getHours();
      }

      let minutes;
      if (currDate.getMinutes() < 10) {
        minutes = "0" + currDate.getMinutes();
      } else {
        minutes = currDate.getMinutes();
      }

      let seconds;
      if (currDate.getSeconds() < 10) {
        seconds = "0" + currDate.getSeconds();
      } else {
        seconds = currDate.getSeconds();
      }

      let ampm = hours >= 12 ? "PM" : "AM";

      this.mainArray[0].value = this.days[currDate.getDay()]
        .substring(3, 0)
        .toUpperCase();
      this.mainArray[1].value = hours;
      this.mainArray[2].value = " : ";
      this.mainArray[3].value = minutes;
      this.mainArray[4].value = " : ";
      this.mainArray[5].value = seconds;
      this.mainArray[6].value = ampm;
    }, 500);
  },
};
</script>

<style>
.clockClass {
  font-family: "Poiret One", cursive;
  background-color: rgba(0, 0, 0, 0.1);
  color: white;
  margin: auto;
}
.clockClass h1 {
  display: inline-block;
  margin: 0 10px;
  font-weight: bold;
  font-size: 5rem;
}
@media (max-width: 768px) {
  .clockClass {
    text-align: center;
    width: 100%;
    margin: 20px;
  }
  .clockClass h1 {
    display: block;
  }
  #C,
  #E {
    display: none;
  }
}
</style>