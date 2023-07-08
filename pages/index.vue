<template>
  <CThemeProvider>
    <UpperNavbar />
    <CBox pt="82px">
      <Carousel />
      <DiscoverSection />
    </CBox>
    <FooterSection />
  </CThemeProvider>
</template>

<script lang="ts">
import UpperNavbar from "~/components/navigations/upper-navbar.vue";
import DiscoverSection from "~/components/sections/discover-section.vue";
import Carousel from "~/components/sections/carousel.vue";
import FooterSection from "~/components/sections/footer-section.vue";
import { CThemeProvider, CBox } from "@chakra-ui/vue";

export default {
  name: "IndexPage",
  components: {
    CThemeProvider,
    CBox,
    UpperNavbar,
    Carousel,
    DiscoverSection,
    FooterSection,
  },
};
</script>
