<template>
  <CInputGroup>
    <CInputLeftElement
      ><CImage size="24px" src="/icons/movie-icon.svg"
    /></CInputLeftElement>
    <CInput
      pr="40px"
      bg="#00000021"
      border="none"
      w="571px"
      placeholder="Find movie"
      border-radius="10px"
      v-model="keywordProps"
    />
    <CInputRightElement
      ><CImage size="24px" src="/icons/search-icon.svg"
    /></CInputRightElement>
  </CInputGroup>
</template>

<script>
import {
  CInputGroup,
  CInputLeftElement,
  CInputRightElement,
  CInput,
  CImage
} from "@chakra-ui/vue";

export default {
  name: "Searchbar",
  props: ["keyword"],
  computed: {
    keywordProps: {
      get() {
        return this.keyword
      },
      set(val) {
        this.$emit("onChange", val)
      }
    }
  },
  components: {
    CInputGroup,
    CInputLeftElement,
    CInputRightElement,
    CInput,
    CImage
  },
};
</script>
