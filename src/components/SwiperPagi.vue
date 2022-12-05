<script>
import { Pagination } from 'swiper';

export default {
  name: 'SwiperPagi',
  setup() {
    return {
      modules: [Pagination],
    };
  },
};
</script>

<template>
  <div>
    <p>1</p>
    <div class="my-8 w-8 h-1 bg-sky-900 translate-x-[-20px]"></div>
    <div class="movies-pagination"></div>
    <!-- <ul >
      <li class=""><i class="fa-regular fa-circle text-[8px]"></i></li>
      <li class="mt-2"><i class="fa-regular fa-circle text-[8px]"></i></li>
      <li class="mt-2"><i class="fa-regular fa-circle text-[8px]"></i></li>
    </ul> -->
  </div>
</template>
