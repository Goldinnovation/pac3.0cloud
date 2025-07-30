<script>
 
  import CalenderHeader from "$lib/component/calender/header/calenderHeader.svelte";
  import CalenderContentbody from "$lib/component/calender/body/calenderContentbody.svelte";
  import CalenderNavigation from "$lib/component/navigation/calenderNavigation.svelte";
  import NaviagtionOptions from "$lib/component/navigation/naviagtionOptions.svelte";

</script>

<main>

  <div class="navigationArea">
    <div class="w-full h-full gap flex flex-col gap-[1%] p-1">
      <CalenderNavigation/>

      <NaviagtionOptions/>

    </div>
  </div>
  
  <div class="contentArea">
    <div class="w-full h-full gap flex flex-col gap-[1%] p-1">
      <!-- Header -->
      <CalenderHeader/>
      <!-- Calender Body -->
      <CalenderContentbody />
    </div>

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
    /* padding: 0.5%; */
    box-sizing: border-box;
  }

  .navigationArea{
    background: #e9eaec;
    width:4%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5%;
    /* box-sizing: border-box; */
  }

  .contentArea{
    /* background: #3e11f4; */
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5%;
    /* box-sizing: border-box; */
  }
</style>
