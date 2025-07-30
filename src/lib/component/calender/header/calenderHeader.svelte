<script lang="ts">

    let AgendaState = $state(true);
    let roomState = $state(false);
    let patientenState = $state(false);
    let einstellungState = $state(false);
 


    const handleBtnOption = (option: string) => { 
        
        
        switch(option){
            case "Agenda":
                AgendaState = true; 
                roomState = false;
                patientenState = false; 
                einstellungState = false
                break; 
            case "Räume": 
                AgendaState = false; 
                roomState = true;
                patientenState = false; 
                einstellungState = false
                break; 
            case "Patienten": 
                AgendaState = false; 
                roomState = false;
                patientenState = true; 
                einstellungState = false
                break; 
            case "einstellung": 
                AgendaState = false; 
                roomState = false;
                patientenState = false; 
                einstellungState = true
                break; 
        }

        
    }

</script>

<div class="   w-full h-[7%] flex items-center justify-between">
    <!-- Left Header Side Section - Logo, Text -->
    <div class="w-[45%] h-[100%] flex gap-[1%]" >
     <div class="w-[70%] h-[100%] flex items-center">
            <input type="text" class=" bg-gray-100 w-[90%] h-[60%] rounded-[7px] border ">
            <!-- <img src="logo.png" alt="scnalyticsLogo" class="w-[100%] h-[60%]"> -->

     </div>
     <!-- <div class="w-[90%] h-[100%] flex items-center"> -->
            <!-- <h1 class="text-4xl font-semibold font-['Helvetica']">Scanlytics</h1> -->
     <!-- </div> -->
    </div>
    <div  class="w-[50%] h-[100%] flex ">
     
       
          <!-- Right Header Side Section - Button options: Agenda, Räume, Patienten, Finanzen -->
        <div class="w-[100%] h-full flex items-center justify-end pr-1.5">
           

                <div class="w-[20%] h-[81%]  flex flex-col justify-center items-end pr-2">
                    <div>
                        <p class="text-sm">Anton Leitner</p>
                    </div>
                    <div>
                        <p class="text-xs">Chefarzt</p>
                    </div>
                  
                   
                
                </div>
                {#if AgendaState}
                <div 
                on:click={() => handleBtnOption("Agenda")}
                class="bg-[#d40000] w-[6%] h-[81%] flex justify-center items-center border-2 border-[#d40000] rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">


                <div class="w-[65%] h-[70%] flex items-center justify-center">
                    <img src="calw.png" alt="calenderIcon" class="w-[70%]  h-[80%]">
                </div>
            
                </div>
              
                {:else}
                <div 
                on:click={() => handleBtnOption("Agenda")}
                class="bg-white w-[6%] h-[81%] flex justify-center items-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">
                
                <div class="w-[65%] h-[70%] flex items-center justify-center">
                    <img src="calb.png" alt="calenderIcon" class="w-[70%]  h-[80%]">
                </div>
                <!-- <div class="w-[45%] h-[100%] flex items-center pl-[1%] 
               
                sm:text-xs
                md:text-xs
                lg:text-sm
                xl:text-s

               
                
                text-blue-900">
                    <p>Agenda</p>
                </div> -->
                </div>
                {/if}
               
             
                <!-- Room Option -->
<!--           
                {#if roomState}
                <div 
                on:click={() => handleBtnOption("Räume")}
                class="bg-blue-900 w-[20%] h-[70%] flex justify-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">


                <div class="w-[15%] h-[100%] flex items-center justify-center">
                    <img src="room.png" alt="calenderIcon" class="w-[70%]  h-[80%]">
                </div>
                <div class="w-[45%] h-[100%] flex items-center pl-[1%] text-l text-white">
                    <p>Räume</p>
                </div>
                </div>
              
                {:else}
                <div 
                on:click={() => handleBtnOption("Räume")}
                class="bg-white w-[20%] h-[70%] flex justify-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">
                
                <div class="w-[15%] h-[100%] flex items-center justify-center">
                    <img src="roomw.png" alt="calenderIcon" class="w-[70%]  h-[80%]">
                </div>
                <div class="w-[45%] h-[100%] flex items-center pl-[1%] text-l text-blue">
                    <p>Räume</p>
                </div>
                </div>
                {/if}

               
                
                {#if patientenState}
                <div 
                on:click={() => handleBtnOption("Patienten")}
                class="bg-blue-900 w-[20%] h-[70%] flex justify-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">


                <div class="w-[15%] h-[100%] flex items-center justify-center">
                    <img src="userw.png" alt="calenderIcon" class="w-[60%]  h-[70%]">
                </div>
                <div class="w-[45%] h-[100%] flex items-center pl-[1%] text-l text-white">
                    <p>Patienten</p>
                </div>
                </div>
              
                {:else}
                <div 
                on:click={() => handleBtnOption("Patienten")}
                class="bg-white w-[20%] h-[70%] flex justify-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">
                
                <div class="w-[15%] h-[90%] flex items-center justify-center">
                    <img src="userb.png" alt="calenderIcon" class="w-[60%]  h-[70%]">
                </div>
                <div class="w-[45%] h-[100%] flex items-center pl-[1%] text-l text-blue">
                    <p>Patienten</p>
                </div>
                </div>
                {/if}

                {#if einstellungState}
                <div 
                on:click={() => handleBtnOption("einstellung")}
                class="bg-blue-900 w-[20%] h-[70%] flex justify-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">


                <div class="w-[15%] h-[100%] flex items-center justify-center">
                    <img src="setw.png" alt="calenderIcon" class="w-[70%]  h-[80%]">
                </div>
                <div class="w-[45%] h-[100%] flex items-center pl-[1%] text-l text-white">
                    <p>Einstellung</p>
                </div>
                </div>
              
                {:else}
                <div 
                on:click={() => handleBtnOption("einstellung")}
                class="bg-white w-[20%] h-[70%] flex justify-center border-2 border-blue-900 rounded-[50px] cursor-pointer hover:bg-blue-500 hover:bg-blue-900 hover:text-white">
                
                <div class="w-[15%] h-[100%] flex items-center justify-center">
                    <img src="setb.png" alt="calenderIcon" class="w-[70%]  h-[80%]">
                </div>
                <div class="w-[45%] h-[100%] flex items-center pl-[1%] text-l text-blue">
                    <p>Einstellung</p>
                </div>
                </div>
                {/if} 
                -->
        </div>

     
    
      
    </div>
 </div>