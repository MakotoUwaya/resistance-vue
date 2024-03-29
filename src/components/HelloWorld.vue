<template>
  <v-container>
    <v-img
      :src="require('../assets/logo.svg')"
      class="my-3"
      contain
      height="200"
    ></v-img>

    <v-row>
      <v-col cols="12">
        <v-row justify="center">
          <h1 class="display-2 font-weight-bold mb-3">
            {{ msg }}
          </h1>
        </v-row>

        <v-row justify="center">
          <p class="subheading font-weight-regular">
            For help and collaboration with other Vuetify developers,
            <br />please join our online
            <a href="https://community.vuetifyjs.com" target="_blank"
              >Discord Community</a
            >
          </p>
        </v-row>
      </v-col>

      <v-col cols="12">
        <v-row justify="center">
          <h2 class="headline font-weight-bold mb-3">What's next?</h2>
        </v-row>

        <v-row justify="center">
          <a
            v-for="(next, i) in whatsNext"
            :key="i"
            :href="next.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ next.text }}
          </a>
        </v-row>
      </v-col>

      <v-col cols="12">
        <v-row justify="center">
          <h2 class="headline font-weight-bold mb-3">Important Links</h2>
        </v-row>

        <v-row justify="center">
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ link.text }}
          </a>
        </v-row>
      </v-col>

      <v-col cols="12">
        <v-row justify="center">
          <h2 class="headline font-weight-bold mb-3">Ecosystem</h2>
        </v-row>

        <v-row justify="center">
          <a
            v-for="(eco, i) in ecosystem"
            :key="i"
            :href="eco.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ eco.text }}
          </a>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  @Prop({ type: String, default: "undefined" }) msg!: string;

  ecosystem: linkItem[] = [
    {
      text: "vuetify-loader",
      href: "https://github.com/vuetifyjs/vuetify-loader"
    },
    {
      text: "github",
      href: "https://github.com/vuetifyjs/vuetify"
    },
    {
      text: "awesome-vuetify",
      href: "https://github.com/vuetifyjs/awesome-vuetify"
    }
  ];
  importantLinks: linkItem[] = [
    {
      text: "Documentation",
      href: "https://vuetifyjs.com"
    },
    {
      text: "Chat",
      href: "https://community.vuetifyjs.com"
    },
    {
      text: "Made with Vuetify",
      href: "https://madewithvuejs.com/vuetify"
    },
    {
      text: "Twitter",
      href: "https://twitter.com/vuetifyjs"
    },
    {
      text: "Articles",
      href: "https://medium.com/vuetify"
    }
  ];
  whatsNext: linkItem[] = [
    {
      text: "Explore components",
      href: "https://vuetifyjs.com/components/api-explorer"
    },
    {
      text: "Select a layout",
      href: "https://vuetifyjs.com/layout/pre-defined"
    },
    {
      text: "Frequently Asked Questions",
      href: "https://vuetifyjs.com/getting-started/frequently-asked-questions"
    }
  ];
}

interface linkItem {
  text: string;
  href: string;
}
</script>
