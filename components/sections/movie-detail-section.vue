<template>
  <CBox pt="300px" position="relative" bg-color="#000000ab">
    <CBox position="absolute" top="0" left="0" w="full" z-index="-1">
      <CImage w="100vw" src="/imgs/movie-detail-bg.jpg" />
    </CBox>
    <CBox class="block" position="relative">
      <CStack direction="row" spacing="8" pb="8">
        <CBox position="absolute" top="0" left="0">
          <CImage w="220px" h="330px" :src="movie.imgUrl" alt="movie image" />
        </CBox>
        <CBox ml="260px">
          <CText font-weight="medium" font-size="18px">{{ movie.year }}</CText>
          <CText font-weight="semibold" font-size="36px">{{ movie.title }}</CText>
          <CText font-weight="medium" font-size="14px">Fantasy, Action, Adventure</CText>
        </CBox>
      </CStack>
    </CBox>
    <CStack py="4" bg="#00000059" w="full">
      <CStack direction="row" ml="330px">
        <CStack direction="row" pr="4" align="center">
          <CStack direction="row" spacing="2" align="center">
            <CImage src="/icons/star.svg" size="32px" alt="star" />
            <CText font-size="36px" font-weight="semibold">
              {{ movie.rating }}
            </CText>
          </CStack>
          <CBox>
            <CText font-size="12px" font-weight="semibold" color="#FFFFFF80">
              USER SCORE
            </CText>
            <CText font-size="12px" font-weight="medium">
              3621 Votes
            </CText>
          </CBox>
        </CStack>
        <CBox border-left="1px solid" border-right="1px solid" border-color="#9d8f8f59" px="4">
          <CText font-size="12px" font-weight="semibold" color="#FFFFFF80">
            USER SCORE
          </CText>
          <CText font-size="12px" font-weight="medium">
            3621 Votes
          </CText>
        </CBox>
        <CBox px="4">
          <CText font-size="12px" font-weight="semibold" color="#FFFFFF80">
            STATUS
          </CText>
          <CText font-size="12px" font-weight="medium">
            RELEASED
          </CText>
        </CBox>
        <CBox border-left="1px solid" border-right="1px solid" border-color="#9d8f8f59" px="4">
          <CText font-size="12px" font-weight="semibold" color="#FFFFFF80">
            LANGUAGE
          </CText>
          <CText font-size="12px" font-weight="medium">
            ENGLISH
          </CText>
        </CBox>
        <CBox px="4">
          <CText font-size="12px" font-weight="semibold" color="#FFFFFF80">
            BUDGET
          </CText>
          <CText font-size="12px" font-weight="medium">
            $200,000,000.00
          </CText>
        </CBox>
        <CBox border-left="1px solid" border-color="#9d8f8f59" pl="4">
          <CText font-size="12px" font-weight="semibold" color="#FFFFFF80">
            PRODUCTION
          </CText>
          <CText font-size="12px" font-weight="medium">
            DC ENTERTAINMENT
          </CText>
        </CBox>
      </CStack>
    </CStack>
    <CBox bg-color="#ffffff" min-height="700px">
      <CBox ml="330px" pt="8" w="526px" mb="16">
        <CText font-weight="semibold" font-size="14px" color="#FF0000" mb="4">OVERVIEW</CText>
        <CText font-size="14px" line-height="2.5" color="#000000">{{ movie.desc }}</CText>
      </CBox>
      <CBox class="block">
        <CText font-weight="semibold" font-size="14px" color="#FF0000" mb="4">REVIEWS</CText>
        <CStack direction="row" justify="space-between">
          <CBox v-for="review in reviews" :key="review.id">
            <ReviewCard :review="review" />
          </CBox>
        </CStack>
      </CBox>
    </CBox>
  </CBox>
</template>

<script>
import ReviewCard from "../cards/review-card.vue";
import { CBox, CStack, CImage, CText } from "@chakra-ui/vue";
export default {
  name: "MovieDetailSection",
  data() {
    return {
      movie: {},
    };
  },
  computed: {
    reviews() {
      return this.$store.state.reviews;
    }
  },
  created() {
    const movie = this.$store.getters.getMovieBySlug(this.$route.params.title);
    this.$set(this.$data, "movie", movie);
  },
  components: {
    CStack,
    CBox,
    CImage,
    CText,
    ReviewCard,
  },
};
</script>
