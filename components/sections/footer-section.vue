<template>
  <CBox bg-color="#0000004A" mt="50px">
    <CStack
      class="block"
      direction="row"
      justify="space-between"
      h="160px"
      align="center"
    >
      <CText color="#929292" font-size="12px"
        >© 2021 MoovieTime. All rights reserved.</CText
      >
      <CImage w="88px" src="/icons/footer-logo.svg" />
      <CText color="#929292" font-size="12px">Made with NUXT.js</CText>
    </CStack>
  </CBox>
</template>

<script>
import { CBox, CStack, CText, CImage } from "@chakra-ui/vue";

export default {
  name: "FooterSection",
  components: { CBox, CStack, CText, CImage },
};
</script>
