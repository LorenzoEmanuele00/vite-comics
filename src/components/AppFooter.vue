<script>
  export default {
    data() {
      return {
        linksDcComics: [
          "Character",
          "Comics",
          "Movies",
          "Tv",
          "Games",
          "Video",
          "News",
        ],
        linksShop: [
          "Shop DC",
          "Shop DC Collectibles",
        ],
        linksDc: [
          "Character",
          "Comics",
          "Movies",
          "Tv",
          "Games",
          "Video",
          "News",
          "Character",
          "Comics",
          "Movies",
          "Tv",
        ],
        linksSite: [
        "Character",
          "Comics",
          "Movies",
          "Tv",
          "Games",
          "Video",
          "News",
        ],
        followIcon: [
          "../assets/img/footer-facebook.png",
          "../assets/img/footer-twitter.png",
          "../assets/img/footer-pinterest.png",
          "../assets/img/footer-periscope.png",
          "../assets/img/footer-youtube.png",
        ],
        stripIcons: [
          {
            image: "../assets/img/buy-comics-digital-comics.png",
            text: "DIGITAL COMICS",
          },
          {
            image: "../assets/img/buy-comics-merchandise.png",
            text: "DC MERCHANDISE",
          },
          {
            image: "../assets/img/buy-comics-subscriptions.png",
            text: "SUBSCRIPTION",
          },
          {
            image: "../assets/img/buy-comics-shop-locator.png",
            text: "COMICS LOCAL SHOP",
          },
        ]
      }
    },
    methods: {
      getImagePath: function(img) {
        return new URL(img, import.meta.url).href
      }
    }
  }
</script>

<template>
  <footer>

    <div class="strip">
      <div class="container strip-flex">
        <div v-for="icon in stripIcons">
          <img class="buy" :src="getImagePath(icon.image)">
          <div><p class="text">{{ icon.text }}</p></div>
        </div>
      </div>
    </div>

    <!-- MAIN LINKS PART -->
    <div class="container">
      <div class="main">
        <div class="row">
          <div class="col">
            <h3>DC COMICS</h3>
            <ul>
              <li v-for="(link) in linksDcComics">
                <a href="">{{ link }}</a> 
              </li>
            </ul>
            <h3>SHOP</h3>
            <ul>
              <li v-for="(link) in linksShop">
                <a href="">{{ link }}</a> 
              </li>
            </ul>
          </div>
          <div class="col">
            <h3>DC</h3>
            <ul>
              <li v-for="(link) in linksDc">
                <a href="">{{ link }}</a> 
              </li>
            </ul>
          </div>
          <div class="col">
            <h3>SITE</h3>
            <ul>
              <li v-for="(link) in linksSite">
                <a href="">{{ link }}</a> 
              </li>
            </ul>
          </div>
        </div>
        <div class="big-logo">
        </div>
      </div>
    </div>

    <!-- BOTTOM PART -->
    <div class="foot">
      <div class="container">
        <div class="button">
          <a href="">SING-UP NOW</a>
        </div>
        <div class="icon">
          <p>FOLLOW US</p>
          <ul>
            <li v-for="icon in followIcon"><img :src="getImagePath(icon)" alt=""></li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

  footer {
    background-image: url("../assets/img/footer-bg.jpg");
    background-size: cover;

    .strip {
      background-color: rgb(0, 139, 203);
      width: 100%;
      padding: 10px;
      
      .strip-flex {
        @include flex-full(row, space-between, center);
        div {
          display: flex;
          align-items: center;
          .buy {
            scale: .6;
          }
          .text {
            font-size: .8rem
          }
        }
      }
    }
    // MAIN LINKS PART
    .main {
      @include flex(space-between);
      
      .row {
        @include flex(flex-start);
        padding-top: 20px;
        padding-bottom: 20px;
        .col {
          margin-right: 30px;
          h3 {
            padding: 10px 0;
            color: white;
          }
          li {
            list-style: none;
            a {
              text-decoration: none;
              display: block;
              color: rgb(139, 139, 139);
              padding: 2px 0;
            }
          }
        }
      }
      .big-logo {
        background-image: url("../assets/img/dc-logo-bg.png");
        background-size: cover;
        width: 400px;
      }
    }

    // BOTTOM PART
    .foot {
      background-color: rgb(62, 62, 62);
      padding: 20px 0;
      .container {
        @include flex(space-between);
        .button{
          padding: 10px;
          border: 2px solid rgb(0, 145, 255);
          @include flex-full(row, center, center);
          a {
            color: white;
            text-decoration: none;
          }
        }
        .icon{
          @include flex-full(row, space-between, center);
          color: white;
          p {
            padding-right: 20px
          }
          ul {
            @include flex(space-between);
            li {
              padding: 0 20px;
              list-style: none;
            }
          }
        }
      }  
    }
  }
</style>
