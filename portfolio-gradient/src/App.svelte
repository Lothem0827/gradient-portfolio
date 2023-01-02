<script>
  import HeaderNavigation from "./assets/components/HeaderNavigation.svelte";
  import HeaderTextBanner from "./assets/components/HeaderTextBanner.svelte";
  import MainHeading from "./assets/components/MainHeading.svelte";
  import MainButtonList from "./assets/components/MainButtonList.svelte";
  import HeaderText from "./assets/components/HeaderText.svelte";
  import FeaturedWorkNavigation from "./assets/components/FeaturedWorkNavigation.svelte";
  import ImageWrapper from "./assets/components/imagesWrapper/ImageWrapper.svelte";
  import Link from "./assets/buttons/Link.svelte";

  import {
    gradient,
    gradientReverse,
    sectionStyle,
    heading,
  } from "./assets/stores/styles";

  import featuredWork_1 from "./assets/External/images/featuredWork_1.png";
  import featuredWork_2 from "./assets/External/images/featuredWork_2.png";
  import featuredWork_3 from "./assets/External/images/featuredWork_3.png";

  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  import LocomotiveScroll from "locomotive-scroll";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    //smoother

    //end of smoother

    //header animation
    const headerAnimation = gsap.timeline({
      scrollTrigger: {
        trigger: ".banner-trigger",
        // scroller: ".smooth-scroll",
        start: "top 40%",
        end: "bottom top",
        scrub: 1,
        // markers: true,
        //pin: ".going-up",
      },
    });
    //headerAnimation.to(".going-up", { y: -600 });

    //end of header animation
    //banner animation
    const bannerAnimation = gsap.timeline({
      scrollTrigger: {
        trigger: ".banner-trigger",
        // scroller: ".smooth-scroll",
        start: "top 89.5%",
        end: "bottom 27%",
        scrub: 3,
        //markers: true,
        pin: ".going-up",
      },
    });

    bannerAnimation.to(".banner", { rotate: -2, scale: 2 }, "-=1");
    bannerAnimation.to(".banner-r", { rotate: 2, scale: 2 }, "-=1");
    // bannerAnimation.to(".going-up", { y: -200 }, "-=1");
    //end of banner animation

    //featured work animation
    const featuredWorkAnimation = gsap.timeline({
      scrollTrigger: {
        trigger: "#trigger",
        start: "top top",
        end: "bottom top",
        scrub: 2,
        markers: true,
        pin: "#trigger",
        anticipatePin: 0.5,
        // pinType: "fixed",
        //pinSpacing: false,
      },
    });
    featuredWorkAnimation.from("#featured-heading", {
      scale: 0.9,
      transformOrigin: "left",
    });
    featuredWorkAnimation.from("#featured", { y: 800, stagger: 0.1 }, "-=.5");
    //end of featured work animation
  });
</script>

<div class="smooth-scroll overflow-x-hidden">
  <section class="{sectionStyle} h-screen flex flex-col justify-between">
    <div class="going-up">
      <div class="p-5s  ">
        <HeaderNavigation />
        <MainHeading />
      </div>
      <!-- <div class="mt-8s">
        <MainButtonList />
      </div> -->
    </div>
    <div class="banner banner-trigger {gradient} px-4s whitespace-nowrap 	">
      <div class=" -translate-x-full ">
        <HeaderTextBanner
          translateX="80vw"
          headingText="contemporary designer • contemporary designer • contemporary designer • contemporary designer   "
        />
      </div>
    </div>
  </section>

  <section class="{sectionStyle} ">
    <div class=" {gradientReverse} px-4s whitespace-nowrap banner-r ">
      <div class="">
        <HeaderTextBanner
          translateX="-80vw"
          headingText="for modern business • for modern business • for modern business • for modern business"
        />
      </div>
    </div>
  </section>

  <section class="h-10s" />
  <div class="{gradient} h-1s mx-5s" />

  <section
    id="trigger"
    class="{sectionStyle} h-[200vh] p-5s flex flex-col gap-5s mt-6s"
  >
    <div class=" grid grid-cols-12 gap-5s">
      <div class="col-span-12">
        <FeaturedWorkNavigation />
      </div>
      <div id="featured-heading" class="col-span-10">
        <HeaderText headingText="featured work" />
      </div>
      <div class="col-span-2 ">2022</div>

      <div
        id="featured"
        class="col-span-4 flex flex-col gap-6s overflow-visible"
      >
        <ImageWrapper featuredImage={featuredWork_1} />
        <h1 class="{heading} {gradient} text-transparent bg-clip-text text-8v">
          teeraco.
        </h1>
      </div>
      <div id="featured" class="col-span-4 flex flex-col gap-6s">
        <ImageWrapper featuredImage={featuredWork_2} />
        <p class="w-5/6">
          Teeraco is a print-on-demand store that sells plant-inspired products
          such as t-shirts, sweatshirts, mugs, and phone cases.
        </p>
      </div>
      <div id="featured" class="col-span-4 flex flex-col gap-6s">
        <ImageWrapper featuredImage={featuredWork_3} />
        <div class="self-end">
          <Link text="view full project" />
        </div>
      </div>
    </div>
  </section>
</div>
