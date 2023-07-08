<template>
  <CStack direction="row" justify="space-between" align="center">
    <CBox>
      <CMenu>
        <CMenuButton
          variant="ghost"
          font-size="14px"
          variant-color="blue"
          border="none"
          font-weight="semibold"
          color="#ffffff"
          cursor="pointer"
        >
          <CImage src="/icons/thumbnail-icon.svg" size="24px" color="#ffffff" />
          &nbsp;&nbsp; CATEGORIES
        </CMenuButton>
        <CMenuList bg-color="#ffffff" p="10px" w="153px" z-index="2">
          <CMenuItem
            v-for="menu, i in menuList"
            :key="i + 1"
            border="none"
            bg-color="#ffffff"
            p="0"
          >
            <CLink
              font-size="12px"
              font-weight="semibold"
              color="#000000"
              as="router-link"
              :to="menu.link"
              cursor="pointer"
              w="full"
              p="10px"
              text-transform="uppercase"
            >
              {{ menu.name }}
            </CLink>
          </CMenuItem>
        </CMenuList>
      </CMenu>
    </CBox>
    <CBox>
      <CStack
        spacing="8"
        direction="row"
        justify="space-between"
        align="center"
      >
        <CLink
          font-size="14px"
          font-weight="semibold"
          as="router-link"
          to="/movies"
        >
          MOVIES
        </CLink>
        <CLink
          font-size="14px"
          font-weight="semibold"
          as="router-link"
          to="/tv-shows"
        >
          TV SHOWS
        </CLink>
        <CLink
          font-size="14px"
          font-weight="semibold"
          as="router-link"
          to="/login"
        >
          LOGIN
        </CLink>
      </CStack>
    </CBox>
  </CStack>
</template>

<script lang="ts">
import { menuList } from "~/constants";
import {
  CBox,
  CImage,
  CStack,
  CMenu,
  CMenuButton,
  CMenuList,
  CMenuItem,
  CLink,
} from "@chakra-ui/vue";

export default {
  name: "Searchbar",
  data() {
    return { menuList };
  },
  components: {
    CBox,
    CImage,
    CStack,
    CMenu,
    CMenuButton,
    CMenuList,
    CMenuItem,
    CLink,
  },
};
</script>
