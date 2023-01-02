<script>
  import { largeButton } from "../stores/styles";
  import { gsap, Sine } from "gsap";
  import { onMount } from "svelte";

  export let text;
  let box, box1;

  const animate = gsap.timeline({ paused: true });

  onMount(() => {
    animate.to(box1, {
      y: "-100%",
      ease: Sine.easeIn,
      duration: 0.3,
    });
    animate.to(box, {
      y: "-100%",
      ease: Sine.easeIn,
      duration: 0.3,
    });

    animate.play();
    // const animation = new Promise((resolve) => {
    //   resolve(animate.play());
    // });

    // animation.then((result) => animate.pause());
  });
</script>

<div
  on:mouseenter={() => animate.play()}
  on:mouseleave={() => animate.reverse()}
  class="w-fit rounded-full bg-gradient-to-r from-pink-500 via-red-500 to-yellow-500 p-1 	"
>
  <div
    class=" {largeButton} rounded-full overflow-hidden px-3s bg-background relative"
  >
    <p bind:this={box1} class="">{text}</p>
    <p bind:this={box} class="absolute">{text}</p>
  </div>
</div>

<!-- <div
  on:mouseenter={() => animate.play()}
  on:mouseleave={() => animate.reverse()}
  class="w-fit rounded-full bg-gradient-to-r from-pink-500 via-red-500 to-yellow-500 p-1 	"
>
  <div class=" {largeButton}  rounded-full w-full h-full overflow-hidden ">
    <div class="w-full  px-3s py-2s pb-0 rounded-full bg-background relative">
      <p bind:this={box1} class="">{text}</p>
      <p bind:this={box} class="absolute top-[90px]">{text}</p>
    </div>
  </div>
</div> -->
