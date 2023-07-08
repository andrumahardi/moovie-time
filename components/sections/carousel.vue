<template>
  <CBox
    py="50px"
    overflow="hidden"
    position="relative"
    h="400px"
    bg="radial-gradient(circle, transparent 35%, black 100%)"
  >
    <CStack
      direction="row"
      spacing="10"
      w="calc(120vw)"
      position="absolute"
      top="50px"
      left="50%"
      z-index="-1"
      transform="translateX(-50%)"
    >
      <CStack
        v-for="item, i in carouselItems"
        :key="i + 1"
        direction="row"
        align="center"
        spacing="0"
      >
        <CImage w="243" h="365" :src="item.imgUrl" />
        <CStack bg-color="#000000" p="20px" h="280px" spacing="2" w="250px">
          <CText font-weight="bold">
            <CImage src="/icons/star.svg" />&nbsp;
            {{ item.rating }}
          </CText>
          <CText font-weight="medium" font-size="28px">
            {{ item.title }}
          </CText>
          <CStack direction="row" align="center">
            <CText>
              {{ item.year }}
            </CText>
            <CBox
              w="5px"
              h="5px"
              border-radius="50%"
              bg-color="rgba(255, 255, 255, 0.5)"
            />
            <CText>
              {{ item.genre }}
            </CText>
          </CStack>
          <CText font-size="12px">
            {{ item.desc }}
          </CText>
        </CStack>
      </CStack>
    </CStack>
    <CBox position="absolute" bottom="50px" w="full">
      <CStack direction="row" justify="center">
        <CBox w="50px" h="10px" border-radius="10px" bg-color="#E74C3C"></CBox>
        <CBox
          w="10px"
          h="10px"
          border-radius="50%"
          bg-color="rgba(255, 255, 255, 0.5)"
        ></CBox>
        <CBox
          w="10px"
          h="10px"
          border-radius="50%"
          bg-color="rgba(255, 255, 255, 0.5)"
        ></CBox>
        <CBox
          w="10px"
          h="10px"
          border-radius="50%"
          bg-color="rgba(255, 255, 255, 0.5)"
        ></CBox>
      </CStack>
    </CBox>
  </CBox>
</template>

<script>
import { CStack, CBox, CImage, CText } from "@chakra-ui/vue";

export default {
  name: "Carousel",
  computed: {
    carouselItems() {
      return this.$store.state.carouselItems;
    },
  },
  components: { CStack, CBox, CImage, CText },
};
</script>
