<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold">Tags</h2>

        <v-row justify="center mt-3">
          <div
            class="tags-wrapper"
            :class="[alignment ? alignmentLeftClass : alignmentBetweenClass]"
          >
            <div class="tags-list">
              <div class="tags-item" v-for="(tag, i) in tags" :key="i">
                <v-icon v-if="tag.icons" class="subheading mx-1">
                  {{ tag.icons }}
                </v-icon>
                <span class="mx-1">{{ tag.text }}</span>
                <div>
                  <v-icon class="subheading icon">mdi-circle-small</v-icon>
                </div>
              </div>
            </div>
          </div>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "TextTags",
  props: {
    tags: {
      type: Array,
    },
    alignment: {
      type: Boolean,
    },
    alignmentLeftClass: {
      type: String,
    },
    alignmentBetweenClass: {
      type: String,
    },
  },

  data: () => ({}),
};
</script>
<style lang="scss">
.tags-wrapper {
  display: flex;
  width: 100%;
}
.tags-list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  max-width: 800px;
  overflow: hidden;
  :last-child.tags-item .icon {
    display: none;
  }
  :last-child.tags-item {
    margin-right: 0;
  }
}
.tags-item {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  margin-right: 10px;
  width: 100%;
}
.icon {
  position: absolute !important;
  top: 0;
  right: -11%;
}
.left {
  justify-content: flex-start;
}
.between {
  justify-content: space-between;
  .tags-list {
    max-width: none;
  }
}
@media screen and (max-width: 678px) {
  .tags-item {
    max-width: 150px;
    flex-shrink: 0;
  }
}
</style>
