<template>
  <CBox
    position="absolute"
    bg-color="#1A1E24"
    w="full"
    top="45px"
    border-radius="10px"
    z-index="1"
  >
    <CBox px="20px" py="10px" v-if="movieTitles.length > 0">
      <CText py="5px" v-for="title, i in movieTitles" :key="i + 1">
        {{ title }}
      </CText>
    </CBox>
    <CBox px="20px" py="10px" v-if="!movieTitles.length">
      <CText text-align="center"> not found :( </CText>
    </CBox>
  </CBox>
</template>

<script>
import { CBox, CText } from "@chakra-ui/vue";

export default {
  name: "AutoComplete",
  data() {
    return {
      titles: [
        "Wonder Woman 1984",
        "Wonder Woman",
        "Wonder",
        "Wonder Bloodlines",
        "Wonder Womans",
        "Wonder Park",
        "Wonder Boys",
      ],
    };
  },
  props: ["keyword"],
  computed: {
    movieTitles() {
      return this.titles.filter((title) =>
        title.toLowerCase().includes((this.keyword || "").toLowerCase())
      );
    },
  },
  components: { CBox, CText },
};
</script>
