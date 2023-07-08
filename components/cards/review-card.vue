<template>
  <CBox p="8" bg-color="#F9F9F9" border-radius="20px" max-width="534px">
    <CStack direction="row" justify="space-between">
      <CStack direction="row" align="center" spacing="4">
        <CBox bg-color="#1E232B36" w="48px" h="48px" border-radius="50%" />
        <CBox>
          <CText font-size="14px" font-weight="bold" color="#1E232A">
            {{ review.reviewer }}
          </CText>
          <CText font-size="12px" color="#666666">
            {{ review.date }}
          </CText>
        </CBox>
      </CStack>
      <CStack direction="row" bg-color="#C4C4C447" py="2" px="4" border-radius="10px">
        <CImage src="/icons/star.svg" size="17px" />
        <CText color="#000000" font-size="36px" font-weight="semibold">
          {{ review.rating }}
        </CText>
      </CStack>
    </CStack>
    <CBox pt="4">
      <CText font-style="italic" font-size="13px" color="#000000">
        {{ review.review }}
      </CText>
    </CBox>
  </CBox>
</template>

<script>
import { CBox, CStack, CText, CImage, } from "@chakra-ui/vue"
export default {
  name: "ReviewCard",
  props: ["review"],
  components: { CBox, CStack, CText, CImage }
}
</script>