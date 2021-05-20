<template>
  <div class="navbar">
    <h2 class="siteName">lyruna</h2>
    <ul class="navLinks">
      <li>The Token</li>
      <li>Marketplace</li>
      <li>Roadmap</li>
      <li>Team</li>
    </ul>
    <ul class="socialLinks">
      <li class="icon reddit"></li>
      <li class="icon twitter"></li>
      <li class="icon telegram"></li>
      <li class="icon discord"></li>
      <!-- Social media icons from https://www.iconfinder.com/ -->
      <a href="#" class="btnPrimary"><span class="join">Join presale</span></a>
    </ul>
  </div>
</template>

<style lang="scss">
.navbar {
  height: 6rem;
  padding: 0 12.5%;
  border-bottom: 1px solid #6666663f;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
  font-size: 1.1rem;

  ul {
    list-style: none;
    display: flex;
    flex-flow: row nowrap;
    padding: unset;
    justify-content: space-between;
    align-items: center;

    &.navLinks {
      gap: 1.5rem;
      margin-left: 15rem;
    }

    &.socialLinks {
      gap: 1rem;

      li {
        width: 24px;
        height: 24px;

        &.reddit {
          background: url("../assets/reddit.png");
          background-size: 24px;
          filter: opacity(0.5);
        }
        &.twitter {
          background: url("../assets/twitter.png");
          background-size: 24px;
          filter: opacity(0.5);
        }
        &.telegram {
          background: url("../assets/telegram.png");
          background-size: 24px;
          filter: opacity(0.5);
        }
        &.discord {
          background: url("../assets/discord.png");
          background-size: 24px;
          filter: opacity(0.5);
        }
      }
    }
  }
}
</style>