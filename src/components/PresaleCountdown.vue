<template>
  <div class="presale-countdown">
    <div class="coloredSubtitle">Presale started May 06, 2021</div>
    <p>Ends on May 14, 2021 - 13:00 EST</p>
    <div class="countdown">
      <span class="days"><span>4</span><span>Days</span></span>
      <span class="hours"><span>3</span><span>Hours</span></span>
      <span class="minutes"
        ><span>{{ minutes }}</span
        ><span>Minutes</span></span
      >
      <span class="seconds"
        ><span>{{ seconds }}</span
        ><span>Seconds</span></span
      >
    </div>
    <div class="amount-raised-text">
      <span>Amount raised</span>
      <span>{{ ethAmount }}%</span>
    </div>
    <div class="amount-progress-bar">
      <div class="amount-progress" :style="`width: ${ethAmount}%`"></div>
    </div>
    <div class="amount-value">{{ ethAmount }}/100 ETH</div>
    <div class="input-box">
      <input id="eth" class="input" type="text" name="eth" placeholder="0.0" />
      <div class="input--right-text"><span>MAX</span><span>ETH</span></div>
    </div>
    <div class="downArrow">🠗</div>
    <div class="input-box">
      <input id="eth" class="input" type="text" name="eth" placeholder="0.0" />
      <div class="input--right-text">$LYRUNA</div>
    </div>
    <a href="#join-the-presale" class="btnPrimary"
      ><span class="join">Connect wallet</span></a
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      ethAmount: 30,
      seconds: 1,
      minutes: 2,
    };
  },
  watch: {
    ethAmount: {
      handler(value) {
        if (value <= 100) {
          setTimeout(() => {
            this.ethAmount++;
          }, 1000);
        } else this.ethAmount = 10;
      },
      immediate: true,
    },
    seconds: {
      handler(value) {
        if (value > 0) {
          setTimeout(() => {
            this.seconds--;
          }, 1000);
        } else {
          this.seconds = 59;
          this.minutes--;
        }
      },
      immediate: true,
    },
    minutes: function () {
      if (this.minutes == -1) this.minutes = 59;
    },
  },
};
</script>

<style lang="scss">
@import "../assets/_variables.scss";

.presale-countdown {
  width: 40rem;
  height: 40rem;
  margin: auto;
  margin-bottom: 10rem;
  border-radius: 30px;
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column nowrap;
  background-color: white;
  box-shadow: 0 15px 45px -25px #0000003f;

  p {
    font-size: 1.1rem;
  }

  .countdown {
    width: 80%;
    display: flex;
    justify-content: space-around;

    .days,
    .hours,
    .minutes,
    .seconds {
      display: flex;
      align-items: center;
      flex-flow: column;

      :first-child {
        font-size: 4rem;
      }
      :last-child {
        font-size: 1.2rem;
        color: grey;
      }
    }
  }

  .amount-raised-text {
    width: 80%;
    display: flex;
    justify-content: space-between;
    margin-top: 3rem;

    span:last-child {
      color: grey;
    }
  }

  .amount-progress-bar {
    width: 80%;
    height: 0.3rem;
    position: relative;
    z-index: 0;
    margin-top: 0.7rem;
    background-color: lightgrey;
    border-radius: 50px;

    .amount-progress {
      width: 30%;
      height: 100%;
      position: relative;
      z-index: 1;
      background-color: $secondary;
      border-radius: 50px;
      transition: width 0.3s ease;
    }
  }

  .amount-value {
    width: 80%;
    margin-top: 0.7rem;
    margin-bottom: 1rem;
    display: flex;
    flex-direction: row-reverse;
    color: grey;
  }

  .input-box {
    width: 70%;
    height: 4rem;
    padding: 0 5%;
    background-color: white;
    border: 1px solid lightgrey;
    border-radius: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 15px 45px -25px #0000003f;

    input.input,
    input.input:focus {
      width: 75%;
      border: none;
      outline: 0;
    }

    .input--right-text {
      width: 20%;
      display: flex;
      justify-content: space-between;
      font-weight: bold;
      text-align: right;

      :first-child {
        color: $secondary;
      }
    }
  }

  .downArrow {
    font-size: 2rem;
    margin: 0.7rem 0;
    color: $secondary;
  }

  .btnPrimary {
    margin-top: 1rem;
  }
}
</style>