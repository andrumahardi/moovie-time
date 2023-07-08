<template>
  <CBox position="relative">
    <CBox
      position="absolute"
      top="0"
      left="0"
      w="full"
      h="333px"
      bg-color="#FFFFFF0D"
      z-index="0"
    />
    <CBox class="block" py="8">
      <CStack direction="row" justify="space-between" align="center" py="8">
        <CBox>
          <CBox
            w="112px"
            h="6px"
            border-radius="5px"
            bg-color="#E74C3C"
            mb="2"
          />
          <CText font-size="24px" font-weight="semibold">
            Discover Movies
          </CText>
        </CBox>
        <CStack direction="row" align="center">
          <DiscoverSectionSorter />
          <CButton
            ml="10px"
            font-size="14px"
            font-weight="semibold"
            color="#ffffff"
            cursor="pointer"
            border-radius="20px"
            bg-color="#00000033"
            >Release Date</CButton
          >
        </CStack>
      </CStack>
      <CGrid template-columns="repeat(5, 1fr)" row-gap="4" column-gap="0">
        <CStack v-for="(movie, i) in movies" :key="i + 1" align="center">
          <MovieCard :movie="movie" />
        </CStack>
      </CGrid>
    </CBox>
  </CBox>
</template>

<script>
import MovieCard from "../cards/movie-card.vue";
import DiscoverSectionSorter from "../buttons/discover-section-sorter.vue";
import { CBox, CGrid, CStack, CDivider, CText, CButton } from "@chakra-ui/vue";

export default {
  name: "DiscoverSection",
  computed: {
    movies() {
      return this.$store.getters.getMovies(10);
    },
  },
  components: {
    CStack,
    CGrid,
    CBox,
    MovieCard,
    CDivider,
    CText,
    CButton,
    DiscoverSectionSorter,
  },
};
</script>
