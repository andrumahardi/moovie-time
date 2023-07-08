<template>
  <CBox bg="#0E1723" border-radius="10px">
    <CBox p="4" border-bottom="1px solid" border-color="#9d8f8f59">
      <CText font-weight="semibold"> Sort Result By </CText>
    </CBox>
    <CBox px="4" py="8">
      <CMenu>
        <CMenuButton
          font-size="14px"
          bg-color="#2f363f"
          font-weight="semibold"
          color="#ffffff"
          border-radius="10px"
          display="flex"
          justify-content="space-between"
          w="full"
        >
          Popularity&nbsp;&nbsp;
          <CBox class="img-wrapper" transform="rotate(180deg)">
            <CImage size="10px" src="/icons/caret.svg" alt="caret" />
          </CBox>
        </CMenuButton>
        <CMenuList bg-color="#111419" p="10px" w="153px" z-index="2">
          <CMenuItem
            v-for="(sortBy, i) in sortVariables"
            :key="i + 1"
            bg-color="#111419"
            border="none"
            p="0"
          >
            <CText font-size="12px" p="10px">
              {{ sortBy }}
            </CText>
          </CMenuItem>
        </CMenuList>
      </CMenu>
    </CBox>
    <CBox
      p="4"
      border-top="1px solid"
      border-bottom="1px solid"
      border-color="#9d8f8f59"
    >
      <CText font-weight="semibold"> Genres </CText>
    </CBox>
    <CStack py="4" w="250px" spacing="1">
      <CStack
        v-for="(menu, i) in menuList"
        :key="i + 1"
        direction="row"
        justify="space-between"
        bg="none"
        w="full"
        as="button"
        px="4"
        py="2"
      >
        <CText text-transform="capitalize">{{ menu.name }}</CText>
        <CCheckbox :is-checked="menu.link === `/${category}`"></CCheckbox>
      </CStack>
    </CStack>
  </CBox>
</template>

<script>
import { menuList, sortVariables } from "~/constants";
import {
  CBox,
  CText,
  CStack,
  CCheckbox,
  CMenu,
  CMenuItem,
  CMenuList,
  CMenuButton,
  CImage,
} from "@chakra-ui/vue";

export default {
  name: "SortActions",
  data() {
    return {
      menuList,
      sortVariables,
      category: "",
    };
  },
  created() {
    this.$set(this.$data, "category", this.$route.params.category);
  },
  components: {
    CBox,
    CText,
    CStack,
    CCheckbox,
    CMenu,
    CMenuItem,
    CMenuList,
    CMenuButton,
    CImage,
  },
};
</script>
