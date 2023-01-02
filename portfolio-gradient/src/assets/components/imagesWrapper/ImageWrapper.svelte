<script>
  export let featuredImage;
  //   import { onMount } from "svelte";
  //   import { gsap } from "gsap";
  //   import { ScrollTrigger } from "gsap/ScrollTrigger";

  //   let img;
  //   onMount(() => {
  //     gsap.registerPlugin(ScrollTrigger);

  //     gsap.to(img, {
  //       scrollTrigger: "#c",
  //       y: 400,
  //       duration: 5,
  //     });
  //   });
</script>

<div class=" flex justify-center select-none overflow-hidden ">
  <img
    class="w-full object-cover hover:scale-125 ease-out duration-300 hover:-rotate-12"
    src={featuredImage}
    alt="hero"
  />
</div>
