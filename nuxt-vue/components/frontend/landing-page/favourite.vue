<template>
  <section id="iq-favorites">
    <b-container fluid>
      <b-row>
        <b-col sm="12" class="overflow-hidden">
          <div class="iq-main-header d-flex align-items-center justify-content-between">
            <div>
              <h4 v-b-tooltip.hover class="main-title" title="View All">
                <nuxt-link to="/frontend/movie-category" class="text-white">
                  Your Favorites
                </nuxt-link>
              </h4>
            </div>
            <div class="d-flex slick-aerrow-block">
              <button
                class="slick-prev slick-arrow"
                aria-label="Previous"
                type="button"
                style="display: block;"
                @click="prev()"
              />
              <button
                class="slick-next slick-arrow"
                aria-label="Next"
                type="button"
                style="display: block;"
                @click="next()"
              />
            </div>
          </div>
          <div class="upcoming-contens">
            <VueSlickCarousel ref="dSlick" v-bind="favOption" class="favorites-slider list-inline row p-0 mb-0">
              <li v-for="(item,index) in favoriteData" :key="index" class="slide-item">
                <nuxt-link to="/frontend/movie-detail">
                  <div class="block-images position-relative">
                    <div class="img-box">
                      <img :src="item.image" class="img-fluid" alt="">
                    </div>
                    <div class="block-description">
                      <h6>{{ item.title }}</h6>
                      <div class="movie-time d-flex align-items-center my-2">
                        <div class="badge badge-secondary p-1 mr-2">
                          {{ item.age }}
                        </div>
                        <span class="text-white">{{ item.time }}</span>
                      </div>
                      <div class="hover-buttons">
                        <span class="btn btn-hover"><i class="fa fa-play mr-1" aria-hidden="true" />
                          Play Now
                        </span>
                      </div>
                    </div>
                    <div class="block-social-info">
                      <ul class="list-inline p-0 m-0 music-play-lists">
                        <li><span><i class="ri-volume-mute-fill" /></span></li>
                        <li><span><i class="ri-heart-fill" /></span></li>
                        <li><span><i class="ri-add-line" /></span></li>
                      </ul>
                    </div>
                  </div>
                </nuxt-link>
              </li>
            </VueSlickCarousel>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
export default {
  name: 'Favourite',
  components: {
    VueSlickCarousel
  },
  data () {
    return {
      favoriteData: [
        { image: require('../../../assets/images/frontend/favorite/01.jpg'), title: 'The Last Breath', age: '5+', time: '2h 30m' },
        { image: require('../../../assets/images/frontend/favorite/02.jpg'), title: 'Last Night', age: '22+', time: '2h 30m' },
        { image: require('../../../assets/images/frontend/favorite/03.jpg'), title: '1980', age: '25+', time: '2h 30m' },
        { image: require('../../../assets/images/frontend/favorite/04.jpg'), title: '1980', age: '25+', time: '2h 30m' },
        { image: require('../../../assets/images/frontend/favorite/05.jpg'), title: '1980', age: '25+', time: '2h 30m' }
      ],
      favOption: {
        dots: false,
        arrows: false,
        infinite: true,
        speed: 300,
        autoplay: false,
        slidesToShow: 4,
        slidesToScroll: 1,
        responsive: [
          {
            breakpoint: 1200,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 1,
              infinite: true,
              dots: true
            }
          },
          {
            breakpoint: 768,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1
            }
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1
            }
          }
        ]
      }
    }
  },
  mounted () {
  },
  methods: {
    next () {
      this.$refs.dSlick.next()
    },
    prev () {
      this.$refs.dSlick.prev()
    }
  }
}
</script>
