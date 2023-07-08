<template>
  <CBox>
    <CMenu>
      <CMenuButton
        font-size="14px"
        bg-color="#FF0000"
        font-weight="semibold"
        color="#ffffff"
        cursor="pointer"
        border-radius="20px"
        class="expand-btn"
      >
        Popularity&nbsp;&nbsp;
        <CBox class="img-wrapper">
          <CImage size="10px" src="/icons/caret.svg" alt="caret" />
        </CBox>
      </CMenuButton>
      <CMenuList bg-color="#111419" p="10px" w="153px" z-index="2">
        <CMenuItem
          v-for="sortBy, i in sortVariables"
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
</template>

<script>
import { sortVariables } from "~/constants";
import {
  CMenu,
  CMenuList,
  CMenuItem,
  CText,
  CMenuButton,
  CImage,
  CBox,
} from "@chakra-ui/vue";

export default {
  name: "DiscoverSectionFilter",
  data() {
    return {
      sortVariables,
    };
  },
  components: [CMenu, CMenuList, CMenuItem, CText, CMenuButton, CImage, CBox],
};
</script>

<style scoped>

.expand-btn {
  width: 125px;
  transition: all .5s;
}

.img-wrapper {
  transform: rotate(90deg);
  opacity: 0;
  transition: transform .5s;
}
.expand-btn:hover {
  background-color: #2f363f;
  border-radius: 5px;
  width: 200px;
  display: flex;
  justify-content: space-between;
}
.expand-btn:hover > .img-wrapper {
  opacity: 1;
  transform: rotate(0deg);
}
</style>
