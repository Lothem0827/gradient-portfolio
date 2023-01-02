<script>
  import Link from "../buttons/Link.svelte";
  import Logo from "../External/svg/Logo.svg";
  import { gradient } from "../stores/styles";
</script>

<header class="flex flex-col ">
  <div class="flex flex-wrap justify-between items-center ">
    <img src={Logo} alt="Logo" />

    <div class="flex justify-end">
      <Link text="menu" />
    </div>
  </div>

  <div class="{gradient} h-1s mt-5s" />
</header>
