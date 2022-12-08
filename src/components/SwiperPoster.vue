<script>
import { Pagination } from 'swiper';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/pagination';

export default {
  name: 'SwiperPoster',
  props: ['movies'],
  setup() {
    const pagination = {
      clickable: true,
      type: 'bullets',
    };
    return {
      modules: [Pagination],
      pagination,
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
};
</script>
<template class="">
<div class="SwiperPoster w-[976px] relative">
  <div class="SwiperPoster-nav">
    <ul class="flex uppercase">
      <li class="mr-8"><a href="">featured</a></li>
      <li class="mr-8"><a href="">coming soon</a></li>
      <li class="mr-8"><a href="">in theaters</a></li>
      <li class="mr-8"><a href="">own it</a></li>
      <li class="mr-8"><a href="">awards winners</a></li>
    </ul>
  </div>
  <swiper class="SwiperPoster-movies mt-8"
  :modules="modules"
  :slides-per-view="4"
  :space-between="50"
  :pagination="pagination">
    <swiper-slide class="SwiperPoster-movie w-[220px] h-auto"
    v-for="movie in movies" :key="movie.title">
      <img :src="movie.poster" class="w-[200px] h-[315px] img-center-cover"
      alt="">
      <a href="" class="after: w-full h-full absolute top-0"></a>
      <h6 class="mt-4 text-lg font-bold">{{movie.title}}</h6>
      <span class=" text-slate-500">{{movie.tag}}</span>
    </swiper-slide>
  </swiper>
</div>
</template>
