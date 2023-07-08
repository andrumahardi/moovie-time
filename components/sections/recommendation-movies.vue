<template>
  <CBox class="block" pt="20">
    <CBox mb="8">
      <CText font-size="14px" font-weight="semibold">RECOMMENDATION MOVIES</CText>
    </CBox>
    <CGrid template-columns="repeat(5, 1fr)" gap="8">
      <CStack v-for="(movie, i) in movies" :key="i + 1" align="center">
        <MovieCard :movie="movie" />
      </CStack>
    </CGrid>
  </CBox>
</template>

<script>
import MovieCard from "../cards/movie-card.vue"
import { CBox, CText, CGrid, CStack } from "@chakra-ui/vue";
export default {
  name: "RecommendationMovies",
  computed: {
    movies() {
      return this.$store.getters.getRecommendedMovies
    }
  },
  components: {
    CBox,
    CText,
    CGrid,
    CStack,
    MovieCard,
  }
}
</script>