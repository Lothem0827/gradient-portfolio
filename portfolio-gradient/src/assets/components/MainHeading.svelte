<script>
  import { gradient } from "../stores/styles"; //./assets/stores/styles
  import arrow from "../External/svg/Arrow.svg";
  import HeaderText from "./HeaderText.svelte";
</script>

<div class="grid grid-cols-12 gap-5s mt-7s ">
  <div class=" col-span-11	">
    <HeaderText headingText="visual designer based in cebu, ph." />
  </div>
  <div class="self-start justify-self-end ">
    <img src={arrow} alt="arrow down" />
  </div>

  <div class="{gradient} col-span-12 h-0.5" />

  <div class=" col-span-3  ">carolino villarta jr.</div>
  <div class=" col-span-3 ">pixeline.freelance@gmail.com</div>
  <div class=" col-span-2 " />
  <div class=" col-span-3 w-[70%] ">
    <p>
      I focused on designing digital experience on both web and mobile
      applications.
    </p>
  </div>

  <div class="{gradient} col-span-12 h-0.5" />
</div>
