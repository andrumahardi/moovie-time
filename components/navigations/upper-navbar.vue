<template>
  <div class="wrapper">
    <CStack
      class="block"
      direction="row"
      justify="space-between"
      align="center"
    >
      <CLink as="router-link" to="/" border="none">
        <CImage
          w="112px"
          src="/icons/upper-navbar-logo.svg"
          alt="navbar-logo"
        />
      </CLink>
      <CBox position="relative">
        <Searchbar :keyword="keyword" @onChange="onChange" />
        <AutoComplete v-if="keyword.length" :keyword="keyword" />
      </CBox>
      <CBox>
        <NavbarButtonGroups />
      </CBox>
    </CStack>
  </div>
</template>

<script>
import Searchbar from "../navigations/searchbar.vue";
import AutoComplete from "../sections/auto-complete.vue";
import NavbarButtonGroups from "../buttons/navbar-button-groups.vue";
import { CBox, CImage, CStack, CLink } from "@chakra-ui/vue";

export default {
  name: "UpperNavbar",
  data() {
    return {
      keyword: "",
    };
  },
  methods: {
    onChange(e) {
      this.keyword = e;
    },
  },
  components: {
    CBox,
    CImage,
    CLink,
    CStack,
    NavbarButtonGroups,
    Searchbar,
    AutoComplete,
  },
};
</script>

<style scoped>
.wrapper {
  background-color: #FFFFFF0D;
  padding: 20px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  z-index: 1000;
}
</style>
