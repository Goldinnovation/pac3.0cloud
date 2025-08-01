<script  lang="ts" module>

    let patientdata = $state("")

   

// export function handlePatientDataOnAgenda(data: any){
//     console.log('data', data.title);
    
//     patientdata = data.title
// }
</script>

<script>
      let patientdata = $state("")
     let {eventData} = $props()


   
     $effect(()  => {
      
        if(eventData){
            patientdata = eventData.title
        }
      
     })

   


</script>


<div class="p-1 h-full bg-pink-200">

   
    {patientdata}
  
    
</div>