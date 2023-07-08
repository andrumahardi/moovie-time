<template>
  <CBox w="220px">
    <CBox w="full" position="relative">
      <CImage w="full" h="330px" :src="movie.imgUrl" />
      <CStack
        w="full"
        h="330px"
        bg-color="#2f2f2f"
        position="absolute"
        top="0"
        left="0"
        justify="space-evenly"
        align="center"
        z-index="1"
        opacity="0"
        transition="all .5s"
        class="hover-trigger"
      >
        <CStack direction="row" align="center">
          <CImage src="/icons/star.svg" size="32px" />&nbsp;
          <CText font-weight="bold">
            {{ movie.rating }}
          </CText>
        </CStack>
        <CText font-size="18px" font-weight="semibold">
          {{ movie.genre }}
        </CText>
        <CLink
          bg-color="#FF0000"
          border-radius="20px"
          py="10px"
          px="25px"
          font-size="14px"
          font-weight="bold"
          as="router-link"
          :to="movie.link"
        >
          VIEW
        </CLink>
      </CStack>
      <CBox
        py="10px"
        px="15px"
        position="absolute"
        top="0"
        right="0"
        bg-color="rgba(30, 35, 43, 0.8)"
      >
        <CText font-weight="bold">
          {{ movie.rating }}
        </CText>
      </CBox>
    </CBox>
    <CBox w="full">
      <CText font-weight="semibold" my="2" isTruncated>{{ movie.title }}</CText>
      <CText color="#929292" font-size="14px">{{ movie.year }}</CText>
    </CBox>
  </CBox>
</template>

<script>
import { CBox, CImage, CText, CStack, CLink } from "@chakra-ui/vue";

export default {
  name: "MovieCard",
  props: ["movie"],
  components: {
    CBox,
    CImage,
    CText,
    CStack,
    CLink,
  },
};
</script>

<style scoped>
.hover-trigger:hover {
  opacity: 1;
}
</style>
