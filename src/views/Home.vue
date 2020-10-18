<template>
  <div>
    <header>
      <nav ref="nav">
        <div class="nav-closed">
          <router-link to="/"
            ><img
              src="/img/logo.png"
              alt="logo"
              style="width: 8rem; height: 6rem"
          /></router-link>
          <ul class="nav-links">
            <li v-on:click="animate()" class="nav-button">
              <a href="#">Products</a>
            </li>
            <li><router-link to="/about">About Us</router-link></li>
            <li><a href="#">Contacts</a></li>
          </ul>
        </div>
        <div ref="navOpen" class="nav-open">
          <div class="products">
            <h2>Products</h2>
            <ul>
              <li><a href="#">Pure Honey</a></li>
              <li><a href="#">Cosmetics</a></li>
              <li><a href="#">Pripolis</a></li>
              <li><a href="#">Process Honey</a></li>
            </ul>
          </div>
          <div class="nav-images">
            <img src="/img/honey_jar.jpg" alt="honey_jar" />
            <img src="/img/cosmetics.jpg" alt="cosmetics" />
          </div>
        </div>
      </nav>
      <div ref="cover" class="cover">
        <img src="/img/mullet.jpg" alt="comb_mullet" />
        <div ref="headline" class="headline">
          <h1>Liquid Sunshine</h1>
          <h1>As sweet as can Bee...</h1>
        </div>
      </div>
    </header>
  </div>
</template>

<script>
import { TimelineLite, Power2 } from "gsap";

const tl_1 = new TimelineLite({ paused: true, reversed: true });
const tl_2 = new TimelineLite();

export default {
  name: "Home",
  mounted() {
    const { cover, nav, navOpen, headline } = this.$refs;

    tl_2
      .fromTo(
        cover,
        2,
        {
          height: "0%",
        },
        {
          height: "100%",
          ease: Power2.easeInOut,
        }
      )
      .fromTo(
        nav,
        1,
        {
          opacity: 0,
        },
        {
          opacity: 1,
          ease: Power2.easeInOut,
        }
      )
      .fromTo(
        headline,
        1,
        {
          opacity: 0,
          x: 30,
        },
        {
          opacity: 1,
          x: 0,
        },
        "-=0.5"
      );

    tl_1
      .to(cover, 1, {
        width: "60%",
        ease: Power2.easeOut,
      })
      .to(
        nav,
        1,
        {
          height: "100%",
          ease: Power2.easeOut,
        },
        "-=0.5"
      )
      .fromTo(
        navOpen,
        0.5,
        {
          opacity: 0,
          x: 50,
          ease: Power2.easeOut,
        },
        {
          opacity: 1,
          x: 0,
          onComplete: function () {
            navOpen.style.pointerEvents = "auto";
            // console.log("Done");
          },
        }
      );
  },
  methods: {
    animate(e) {
      if (tl_1.isActive()) {
        e.preventDefault();
        e.stopImediatePropagation();
      }

      this.toggleTween(tl_1);
    },
    toggleTween(tween) {
      tween.reversed() ? tween.play() : tween.reverse();
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  width: 100%;
  font-family: "Raleway", sans-serif;
  /* background: black; */
  background: #fef5cb;
}

header {
  height: 100vh;
  position: relative;
  display: flex;
}

.cover {
  height: 100%;
  position: absolute;
  width: 100%;
  top: 0;
  right: 0;
}

.cover img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

.headline {
  position: absolute;
  right: 0;
  margin-top: -25%;
  margin-right: 8%;
  text-align: right;
  z-index: 4;
}

.headline h1 {
  font-size: 4rem;
  color: whitesmoke;
}

nav {
  background: whitesmoke;
  z-index: 2;
  width: 40%;
  height: 20%;
  color: #f3b21b;
  /* overflow: hidden; */
}

.nav-closed {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 20%;
  width: 40%;
  position: absolute;
}

.nav-closed ul {
  display: flex;
  width: 60%;
  justify-content: space-around;
  list-style: none;
}

.nav-links li a {
  text-decoration: none;
  color: #f3b21b;
}

.nav-open {
  position: absolute;
  width: 40%;
  height: 80%;
  top: 20%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  opacity: 0;
  pointer-events: none;
}

.products {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
}

.products h2 {
  font-size: 50px;
}

.products ul li {
  padding-bottom: 10px;
}

.products ul {
  list-style: none;
}

.nav-images {
  display: flex;
  justify-content: space-around;
  width: 100%;
}

.nav-images img {
  width: 12rem;
  height: 24rem;
  object-fit: cover;
  object-position: center;
}

.products ul li a {
  text-decoration: none;
  color: #f3b21b;
}

.nav-images img {
  height: 250px;
}
</style>