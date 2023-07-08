<template>
  <CThemeProvider>
    <UpperNavbar />
    <CBox pt="82px">
      <CategorySection />
    </CBox>
    <FooterSection />
  </CThemeProvider>
</template>

<script lang="ts">
import UpperNavbar from "~/components/navigations/upper-navbar.vue";
import FooterSection from "~/components/sections/footer-section.vue";
import CategorySection from "~/components/sections/category-section.vue";
import { CThemeProvider, CBox } from "@chakra-ui/vue";

export default {
  name: "CategoryPage",
  components: {
    CThemeProvider,
    CBox,
    UpperNavbar,
    FooterSection,
    CategorySection
  },
};
</script>
