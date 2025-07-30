<script>
  import Calenderheader from "$lib/component/calender/body/calenderHeader.svelte";
  import CalenderContentbody from "$lib/component/calender/header/calenderContentbody.svelte";
</script>

<main>
  <div class="w-full h-full gap flex flex-col gap-[1%] p-1">
    <!-- Header -->
    <Calenderheader />
    <!-- Calender Body -->
    <CalenderContentbody />
  </div>
</main>

<style>
  main {
    background: #ffffff;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    /* padding: 0.4%; */
    box-sizing: border-box;
  }
</style>
