<template>
  <v-container>
    <v-row no-gutters>
      <v-col cols="12" class="pos1">
        <h1
          class="monserrat text-center spaced white--text"
        >
          {{ datas.name }}
        </h1>
      </v-col>

      <v-col class="pos2">
        <v-card
          class="mx-auto align-end"
          color="rgba(221,10,125,1)"
          elevation="24"
          height="60vh"
          width="50%"
        >
          <v-img
            class="mx-auto img"
            src="@/assets/aquila3.png"
            height="46%"
            width="38%"
            contain
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
    <v-row
      align="center"
      justify="center"
      class="mx-auto pos3"
    >
      <v-col
        class="text-center"
      >
        <v-btn
          class="font-weight-light"
          dark
          text
        >
          HOME
        </v-btn>
      </v-col>
      <v-col
        class="text-center"
      >
        <v-btn
          class="font-weight-light"
          dark
          text
        >
          ABOUT
        </v-btn>
      </v-col>
      <v-col>
        <v-row
          class="font-weight-light"
          justify="center"
        >
          <v-avatar
            size="78"
          >
            <img
              src="@/assets/aquila.jpg"
              alt="John"
            >
          </v-avatar>
        </v-row>
      </v-col>
      <v-col
        class="text-center"
      >
        <v-btn
          class="font-weight-light"
          dark
          text
        >
          GALLERY
        </v-btn>
      </v-col>
      <v-col
        class="text-center"
      >
        <v-btn
          class="font-weight-light"
          dark
          text
        >
          CONTACT
        </v-btn>
      </v-col>
    </v-row>
    <div
      class="pos4"
    >
      <v-btn
        icon
        class="mb-4"
        :href="instagramLink"
      >
        <v-icon
          color="white"
        >
          mdi-instagram
        </v-icon>
      </v-btn><br>
      <v-btn
        icon
        class="mb-4"
        :href="twitterLink"
      >
        <v-icon
          color="white"
        >
          mdi-twitter
        </v-icon>
      </v-btn><br>
      <v-btn
        icon
        class="mb-4"
        :href="snapchatLink"
      >
        <v-icon
          color="white"
        >
          mdi-snapchat
        </v-icon>
      </v-btn><br>
      <v-btn
        icon
        class="mb-4"
        :href="emailLink"
      >
        <v-icon
          color="white"
        >
          mdi-email
        </v-icon>
      </v-btn>
   </div>
 
  </v-container>
</template>

<script>
  import axios from 'axios';

  export default {
    name: 'HelloWorld',
    mounted () {
      axios.get("https://hirng-x2021.glitch.me/api" , {
          headers: {}
      })
      .then(response => {
          this.datas = response.data
          console.log(response.data);
      })
      .catch(function (error) {
            console.log(error);
      });
    },
    created () {
      this.linkAm();
    },

    data: () => ({
      datas: '',
    }),
    computed: {
      instagramLink () {
        return `https://instagram.com/${this.datas.social_media.instagram}`;
      },
      twitterLink () {
        return `https://twitter.com/${this.datas.social_media.twitter}`;
      },
      snapchatLink () {
        return `https://snapchat.com/${this.datas.social_media.snapchat}`;
      },
      emailLink () {
        return `mailto:${this.datas.social_media.email}`
      }
    }
  }
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@100;300&display=swap');
  .monserrat {
    font-family: 'Montserrat', sans-serif;
    font-weight: 100;
    font-size: 40px;
  }
  .spaced {
    letter-spacing: 8px;
  }
  .pos1 {
    position: fixed;
    left: 0%;
    right: 0%;
    top: 6%;
  }
  .pos2 {
    position: fixed;
    left: 0%;
    right: 0%;
    top: 20%;
  }
  .pos3 {
    position: fixed;
    top: 86%;
    left: 0%;
    right: 0%;
    max-width: 70%;
  }
  .pos4 {
    position: fixed;
    top: 50%;
    transform: translateY(-50%);
    right: 3%;
  }
  .img {
    position: fixed;
    left: 0%;
    right: 0%;
    top: 35.2%;
  }
</style>