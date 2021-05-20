<template>
  <div class="iphone-mask">
    <div class="status-bar">
      <span class="time">{{ time }}</span>
      <span>
        <img src="../assets/iphone-wifi.png" alt="wifi" width="16" />
        <img src="../assets/iphone-battery.png" alt="battery" width="16" />
      </span>
    </div>
    <div class="iphone-content">
      <div class="iphone-navbar">
        <span>lyruna</span>
        <span>
          <img
            class="iphone-avatar"
            src="https://cdn.dribbble.com/users/12947/avatars/normal/2cc07a586c7b7d71efed54888edd7981.jpg?1613497764"
            alt="Ryan Johnson"
        /></span>
      </div>
      <h4>Exclusive NFT's from your favourite musicians</h4>
      <div class="iphone-search">Search</div>
      <div class="cards">
        <Card
          v-for="(card, i) in cardTitles"
          :key="i"
          :imageId="i + 1"
          :title="card"
          :ethValue="ethValues[i]"
        />
      </div>
    </div>
    <div class="iphone-footer">
      <span>
        <img src="../assets/home.png" alt="wifi" width="16" />
      </span>
      <span>
        <img src="../assets/search.png" alt="battery" width="16" />
      </span>
      <span>
        <img src="../assets/gear.png" alt="battery" width="16" />
      </span>
    </div>
    <div class="line"></div>
  </div>
</template>

<script>
import Card from "./Card";

export default {
  data() {
    return {
      cardTitles: ["Encore", "Mood", "Contact Festival"],
      ethValues: [4.0, 3.1, 2.6],
    };
  },
  computed: {
    time() {
      return new Date().toLocaleTimeString([], {
        hour: "2-digit",
        minute: "2-digit",
      });
    },
  },
  components: {
    Card,
  },
};
</script>

<style lang="scss">
.iphone-mask {
  width: 290px;
  height: 585px;
  position: absolute;
  right: 1rem;
  top: 10rem;
  z-index: 2;
  background-image: url("../assets/transparent-iphone-se.png");
  background-size: 300px;
  background-position: 50%;
  background-repeat: no-repeat;
  background-color: white;
  border-radius: 45px;

  .status-bar {
    display: flex;
    justify-content: space-between;
    position: sticky;
    width: 75%;
    margin: auto;
    margin-top: 1.75rem;

    .time {
      font-size: 0.75rem;
    }
  }

  .iphone-footer {
    width: 87%;
    height: 8%;
    margin: 0 auto;
    display: flex;
    justify-content: space-around;
    align-items: center;
    position: sticky;
    bottom: 0;
    border-top: 1px solid #8080803a;
  }

  .line {
    width: 30%;
    height: 5px;
    margin: 0 auto;
    position: absolute;
    bottom: 1.5rem;
    background-color: black;
    border-radius: 50px;
    right: 0;
    left: 0;
  }

  .iphone-content {
    width: 75%;
    height: 79%;
    margin: auto;
    margin-top: 0;
    overflow-y: scroll;
    overflow-x: hidden;
    scrollbar-color: transparent transparent;
    scrollbar-width: none;

    &::-webkit-scrollbar {
      display: none;
    }
    &::-webkit-scrollbar-thumb {
      display: none;
    }

    .iphone-navbar {
      margin: 0.5rem 0;
      display: flex;
      justify-content: space-between;
      align-items: center;

      .iphone-avatar {
        width: 32px;
        border-radius: 50px;
      }
    }

    h4 {
      text-align: center;
      margin-bottom: 0.5rem;
    }

    .iphone-search {
      width: max-content;
      margin: auto;
      font-size: 0.75rem;
      padding: 0.25rem 0.5rem;
      border: 2px solid #8080803a;
      border-radius: 50px;
    }

    .cards {
      padding: 1rem 0;
      transition: none;
      transition: transform ease 0.2s;

      .card:hover {
        transform: translateY(-0.8rem);
      }
    }
  }
}
</style>