<template>
  <div class="horloge">
    <span class="hour">{{ hour }}:</span>
    <span class="mins">{{ mins }}:</span>
    <span class="secs">{{ secs }}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      now: new Date(),
      intervalID: null,
    };
  },

  computed: {
    hour() {
      return this.now.getHours();
    },
    mins() {
      return this.now.getMinutes();
    },
    secs() {
      return this.now.getSeconds() < 10
        ? `0${this.now.getSeconds()}`
        : this.now.getSeconds();
    },
  },

  beforeMount() {
    this.intervalID = setInterval(() => {
      this.now = new Date();
    }, 1000);
  },
  beforeDestroy() {
    clearInterval(this.intervalID);
  },
};
</script>

<style scoped>
.horloge {
  margin-top: 30px;
  margin-bottom: 30px;
}
span {
  margin: 40px 0 0;
  font-size: 50px;
}
</style>
