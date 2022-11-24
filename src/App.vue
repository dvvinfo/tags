<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <text-tags
        :tags="tags"
        :alignment="(alignment = true)"
        :alignmentLeftClass="alignmentLeftClass"
        :alignmentBetweenClass="alignmentBetweenClass"
      />
      <text-tags
        :tags="tags"
        :alignment="(alignment = false)"
        :alignmentLeftClass="alignmentLeftClass"
        :alignmentBetweenClass="alignmentBetweenClass"
      />
    </v-main>
  </v-app>
</template>

<script>
import TextTags from "@/components/TextTags.vue";
export default {
  name: "App",
  components: {
    TextTags,
  },
  data: () => ({
    tags: [
      {
        text: "mdi-domain",
        icons: "mdi-domain",
      },
      {
        text: "text2",
        icons: "mdi-arrow-up-bold-box-outline",
      },
      {
        text: "text2",
        icons: "mdi-message-text",
      },
      {
        text: "text3",
        icons: "mdi-open-in-new",
      },
      {
        text: "text4",
        icons: "mdi-email",
      },
    ],
    alignment: false,
    alignmentLeftClass: "left",
    alignmentBetweenClass: "between",
  }),
};
</script>
