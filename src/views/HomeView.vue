<script>
import { ref } from 'vue';
import NavComponent from '@/components/NaviGation.vue';
import SwiperPoster from '@/components/SwiperPoster.vue';
import SwiperPagi from '@/components/SwiperPagi.vue';
import FooterNavi from '@/components/FooterNavi.vue';

export default {
  name: 'HomeView',
  components: {
    NavComponent, SwiperPoster, SwiperPagi, FooterNavi,
  },
  setup() {
    const data = ref();
    fetch('http://localhost:3000/movies').then((res) => res.json())
      .then((d) => {
        data.value = d;
      })
      .catch((err) => console.log(err));
    return {
      data,
    };
  },
};
</script>
<template>
<div class="bg-black">
<div class="hero h-screen img-center-cover text-white relative
  bg-[url('https://resize.indiatvnews.com/en/resize/newbucket/1200_-/2022/09/black-adam-1663735185.jpg')]">
  <div class="bg-mask">
    <div class="px-[10%]">
    <NavComponent />
    <div class="content flex justify-between">
      <div class="left flex flex-col justify-center">
        <div class="text ">
          <h1 class="text-9xl">30<span class="block mt-4 text-base">Academy Awards</span></h1>
          <div class="w-1/4 h-2 my-16 border bg-white"></div>
          <h1 class="text-9xl">122<span class="block mt-4 text-base">
            Academy Awards Nominations</span></h1>
        </div>
      </div>
      <div class="right w-[30%]">
        <div class="text">
          <h1 class="text-7xl">LIONSGATE<br>MOVIES</h1>
          <p class="mt-8 leading-8">Lionsgate's feature film production and distribution operation
            encompasses a diverse slate of tentpoles, star-driven event
            films and branded properties</p>
            <div class="mt-16">
              <iframe class="w-[300px] h-auto" width="560" height="315" src="https://www.youtube.com/embed/n-7K_OjsDCQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>
      </div>
    </div>
    </div>
  <div class="bg-bottom-fading"></div>
  </div>
</div>
<div class="mt-8 px-[3%]">
  <div class="flex justify-between items-center bg-white px-[7%] py-8">
  <div class="text flex flex-col justify-center">
    <h1 class="text-5xl  uppercase">drama&romantic</h1>
    <span class="mt-8 text-base font-bold">Exciting, emotional and unexpected.</span>
  </div>
  <SwiperPoster :movies="data" />
  </div>
</div>
<div class="mt-8 px-[3%] text-white">
  <div class="flex justify-between items-center bg-black px-[7%] py-8">
  <SwiperPoster />
  <div class="text flex flex-col justify-center">
    <h1 class="text-5xl  uppercase">action&adventure</h1>
    <span class="mt-8 text-base font-bold">Heroic, physical and frantic.</span>
  </div>
  <SwiperPagi />
  </div>
</div>
<div class="footer px-[10%] py-16 bg-gray-300">
<FooterNavi />
</div>
</div>
</template>

<style scoped>
</style>
