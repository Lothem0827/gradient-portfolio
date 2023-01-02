<script>
  import { heading } from "../stores/styles";
  import gsap from "gsap";
  import { onMount } from "svelte";

  let animate;
  export let headingText;
  export let translateX;

  //C:\Users\penxe\AppData\Local\Programs\Code

  onMount(() => {
    gsap.to(animate, {
      x: translateX,
      repeat: -1,
      yoyo: true,
      duration: 22,
    });
  });
</script>

<h1 bind:this={animate} class=" {heading} text-8v pt-1s  text-background ">
  {headingText}
</h1>
