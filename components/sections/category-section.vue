<template>
  <CBox class="block" py="16">
    <CBox>
      <CBox w="112px" h="6px" border-radius="5px" bg-color="#E74C3C" mb="2" />
      <CText font-size="36px" font-weight="semibold"> Movies </CText>
    </CBox>
    <CStack pt="8" direction="row" justify="space-between">
      <CBox>
        <SortActions />
      </CBox>
      <CBox>
        <CGrid template-columns="repeat(4, 1fr)" gap="8">
          <CStack v-for="(movie, i) in movies" :key="i + 1" align="center">
            <MovieCard :movie="movie" />
          </CStack>
        </CGrid>
        <CStack direction="row" justify="center" pt="8">
          <CButton
            font-size="14px"
            bg-color="#FF0000"
            font-weight="semibold"
            color="#ffffff"
            cursor="pointer"
            border-radius="20px"
          >
            Load More
          </CButton>
        </CStack>
      </CBox>
    </CStack>
  </CBox>
</template>

<script>
import MovieCard from "~/components/cards/movie-card.vue";
import SortActions from "~/components/sections/sort-actions.vue";
import { CBox, CText, CStack, CGrid, CButton } from "@chakra-ui/vue";

export default {
  name: "CategorySection",
  computed: {
    movies() {
      return this.$store.getters.getMovies(12)
    }
  },
  components: {
    MovieCard,
    SortActions,
    CBox,
    CText,
    CStack,
    CGrid,
    CButton,
  },
};
</script>
