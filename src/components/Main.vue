<template>
  <main>
    <div class="chip">Coming Soon</div>
    <div class="coloredTitle">
      Support your<br />favourite musicians<br />through NFT's
    </div>
    <p class="subtitle">
      Get exclusive new releases, unreleased songs, and backstage<br />passes to
      upcoming shows.
    </p>
    <a href="#" class="btnPrimary">
      <span class="join">Join the $LYRUNA presale ➔</span>
    </a>
    <a href="#" class="btnSecondary">
      <span class="join">See our whitepaper</span>
    </a>
    <div class="cards">
      <Card
        v-for="(card, i) in cardTitles"
        :key="i"
        :imageId="i + 1"
        :title="card"
        :ethValue="ethValues[i]"
      />
    </div>
    <div class="rightElements">
      <img
        class="right-img"
        :src="`https://picsum.photos/500/700`"
        alt="image"
      />
      <div class="iphone-shadow-top"></div>
      <div class="iphone-shadow-bottom"></div>
      <Iphone />
    </div>
    <div id="join-the-presale" class="presale-block">
      <div class="center">
        <h1>Join the presale</h1>
        <p>
          Take part in our quest to support musicians by contributing your ETH
          in the presale of $LYRUNA
        </p>
      </div>
      <div class="presale-shadow-top"></div>
      <div class="presale-shadow-bottom"></div>
      <PresaleCountdown />
    </div>
  </main>
</template>

<script>
import Card from "./Card.vue";
import Iphone from "./Iphone.vue";
import PresaleCountdown from "./PresaleCountdown.vue";

export default {
  data() {
    return {
      cardTitles: ["Encore", "Mood", "Contact Festival"],
      ethValues: [4.0, 3.1, 2.6],
    };
  },
  components: {
    Card,
    Iphone,
    PresaleCountdown,
  },
};
</script>

<style lang="scss">
@import "../assets/_variables.scss";
@import "../assets/_button.scss";
@import "../assets/_card.scss";

main {
  width: 75%;
  margin: auto;
  margin-top: 4rem;
  position: relative;

  .chip {
    width: max-content;
    color: #af60ba;
    padding: 0.75rem 1.25rem;
    border-radius: 50px;
    background-color: #f5effc;
    font-weight: bold;
  }

  .coloredTitle {
    margin-top: 2rem;
    width: max-content;
    font-size: 4rem;
    color: black;
    background: linear-gradient(to right, $primary, $secondary);
    background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: 700;
  }

  .coloredSubtitle {
    color: $secondary;
    font-weight: bold;
  }

  .subtitle {
    font-size: 1.5rem;
    line-height: 2.5rem;
    padding-bottom: 1.5rem;
  }

  .btnPrimary,
  .btnSecondary {
    font-size: 1.25rem;
    margin-right: 1.5rem;
  }

  .rightElements {
    position: absolute;
    top: 0;
    right: 5rem;

    img.right-img {
      position: absolute;
      z-index: 0;
      right: 10rem;
      border-radius: 10px 60px 60px 10px;
    }

    .iphone-shadow-top {
      width: 290px;
      height: 185px;
      position: absolute;
      right: 1rem;
      top: 10rem;
      z-index: -1;
      border-radius: 45px;
      box-shadow: 0 0px 455px 0px rgba($primary, 0.7);
    }
    .iphone-shadow-bottom {
      width: 290px;
      height: 185px;
      position: absolute;
      right: 1rem;
      top: 35rem;
      z-index: -1;
      border-radius: 45px;
      box-shadow: 0 0px 455px 0px rgba($secondary, 0.6);
    }
  }

  .center {
    text-align: center;
    p {
      font-size: 1.25rem;
    }
  }

  .presale-block {
    position: relative;
    z-index: 1;

    .presale-shadow-top {
      width: 290px;
      height: 285px;
      position: absolute;
      right: 32%;
      top: 15rem;
      z-index: 0;
      border-radius: 45px;
      box-shadow: 0 0px 455px 0px rgba($secondary, 0.5);
    }
    .presale-shadow-bottom {
      width: 290px;
      height: 185px;
      position: absolute;
      left: 32%;
      bottom: 5rem;
      z-index: 0;
      border-radius: 45px;
      box-shadow: 0 0px 455px 0px rgba(0, 150, 250, 0.7);
    }
  }
}
</style>