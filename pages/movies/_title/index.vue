<template>
  <CThemeProvider>
    <UpperNavbar />
    <CBox>
      <MovieDetailSection />
      <RecommendationMovies />
    </CBox>
    <FooterSection />
  </CThemeProvider>
</template>

<script>
import RecommendationMovies from "../../../components/sections/recommendation-movies.vue";
import UpperNavbar from "../../../components/navigations/upper-navbar.vue";
import FooterSection from "../../../components/sections/footer-section.vue";
import MovieDetailSection from "../../../components/sections/movie-detail-section.vue";
import { CThemeProvider, CBox } from "@chakra-ui/vue";

export default {
  name: "MovieTitlePage",
  components: {
    CThemeProvider,
    CBox,
    UpperNavbar,
    FooterSection,
    MovieDetailSection,
    RecommendationMovies,
  },
};
</script>
