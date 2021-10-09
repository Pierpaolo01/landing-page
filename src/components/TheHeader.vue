<template>
  <div class="header-container flex flex-column">
    <header class="flex">
      <h1>logo</h1>

      <!-- Mobile navigation, only shows on screens < 600px -->
      <nav class="navigation-mobile" v-if="isMobile">
        <button>
          <img src="../assets/icon-hamburger.svg" alt="menu" />
        </button>
      </nav>
      <!-- bigger screen navigation, shows on screens > 600px -->
      <nav class="navigation-desktop flex" v-else>
        <div class="nav-items flex">
          <p>Pricing</p>
          <p>Contact</p>
          <p>Support</p>
        </div>
        <div class="login-btn-container">
          <button class="btn btn-secondary btn-login">Login</button>
          <button class="btn btn-primary btn-singup">Sign Up</button>
        </div>
      </nav>
    </header>

    <main class="flex flex-column">
      <h1 class="slogan">
        A modern <br v-if="isMobile" />
        publishing platform
      </h1>
      <p class="slogan-p">Grow your audience and build your online brand</p>
      <div class="btn-container flex">
        <button class="btn btn-primary">Start for Free</button>
        <button class="btn btn-secondary">Learn More</button>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMobile: null,
    };
  },
  methods: {
    checkScreen() {
      if (window.innerWidth > 770) {
        this.isMobile = false;
        return;
      }
      this.isMobile = true;
    },
  },
  created() {
    this.checkScreen();
    window.addEventListener("resize", this.checkScreen);
  },
};
</script>

<style scoped lang="scss">
.header-container {
  background-color: hsl(353, 100%, 62%);
  color: hsl(0, 0%, 100%);
  max-height: 600px;
  height: 80%;
  padding: 60px min(8%, 165px) 0 min(8%, 165px);
  background-attachment: fixed;
  background-position: bottom center;
  background-repeat: no-repeat;
  background-size: 800px 800px;
  border-bottom-left-radius: 125px;
  background-image: url("../assets/bg-pattern-header.svg");

  font-family: "overpass";

  header {
    margin-bottom: min(110px, 38%);
    justify-content: space-between;
    align-items: center;

    .navigation-desktop {
      width: 85%;
      justify-content: space-between;
      align-items: center;
      
      .nav-items{
        // justify-content: space-evenly;
        p {
          margin: 0 15px;
          text-decoration: underline;
        }
      }


      .btn-login{
        margin-right: 20px;
      }

    }
  }

  main {
    align-items: center;
    width: min(90%, 920px);
    margin: 0 auto 0 auto;
    margin-bottom: min(150px, 38%);

    .btn-container {
      width: 100%;
      justify-content: space-around;
    }
  }

  @media screen and (min-width: 600px) {
    background-size: 1600px 1600px;
    background-position: -100px;

    h1 {
      font-size: 4rem !important;
    }

    .slogan {
      white-space: nowrap;
      overflow: hidden;
      width: 100%;
    }

    p {
      font-size: 1.5rem !important;
    }
  }
  @media screen and (min-width: 1450px) {
    background-position: 550px -500px;
  }

  h1 {
    font-size: 2rem;
    font-weight: 600;
    margin: 0;
  }
  .slogan-p {
    font-size: 1.125rem;
    font-weight: 300;
    margin-bottom: 45px;
  }
  button {
    background: none;
    border: none;
  }
  .btn-primary {
    background-color: hsl(0, 0%, 100%);
    color: hsl(356, 100%, 66%);
  }
  .btn-primary:hover {
    color: hsl(0, 0%, 100%);
    background-color: hsl(355, 100%, 74%);
  }
  .btn-secondary {
    border: 2px solid hsl(0, 0%, 100%);
    color: hsl(0, 0%, 100%);
  }

  .btn-secondary:hover {
    background-color: hsl(0, 0%, 100%);
    color: hsl(356, 100%, 66%);
  }
}
</style>
