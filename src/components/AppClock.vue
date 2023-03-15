<script>
export default {
  mounted() {
    setInterval(() => this.updateTime(), 1000);
  },

  data() {
    return {
      hours: "",
      minutes: "",
      seconds: "",
      period: "",
    }
  },

  methods: {
    updateTime() {
      const date = new Date();
      this.hours = date.getHours();
      this.minutes = date.getMinutes();
      this.seconds = date.getSeconds();
      this.period = this.hours < 12 ? "AM" : "PM";
    }
  }
};

</script>

<template>
  <div class="container">
    <p>{{ hours }}:{{ minutes }}:{{ seconds }} {{ period }}</p>
  </div>
</template>

<style>
body{
  display: flex;
  align-items: center;
}
  .container {
    background-color: rgba(0, 0, 0, 0.713);
    width: 80vw;
    height: 30vw;
    border: 10px solid rgb(3, 1, 1);
    box-shadow: 5px 5px 80px rgba(255, 0, 0, 0.692) inset;
    border-radius: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  p {
    font-size: 10rem;
    color: red;
    text-shadow: 1px 1px 25px red;
  }

</style>
