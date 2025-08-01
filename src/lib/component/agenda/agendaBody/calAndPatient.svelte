

<script
  src="https://cdn.jsdelivr.net/npm/@event-calendar/build@4.5.0/dist/event-calendar.min.js"
>
    import { Calendar, TimeGrid} from "@event-calendar/core";
    import rrulePlugin from '@fullcalendar/rrule'
    import dayGridPlugin from '@fullcalendar/daygrid'   
    import interactionPlugin from '@fullcalendar/interaction';
    import AgendaPatient from "./patient/agendaPatient.svelte";



    let eventData = $state({})
    let eventState = $state(false)

//   calendar.setOption('height', 700);
  let options = $state({
    view: "timeGridWeek",
    slotDuration: '00:30:00',  

    aspectRatio: 5,
    plugins: [ rrulePlugin, dayGridPlugin, interactionPlugin],
    headerToolbar: {
      start: "prev,next",
      center: "",
      end: "title",
    },
    // plugins: [ dayGridPlugin, interactionPlugin ],
    titleFormat: {
      year: "numeric",
      month: "long",
    },

    events: [
        { // this object will be "parsed" into an Event Object
        id: 'a',
        title: 'Petra Lauge (Fuß gebrochen)',
        start: '2025-07-30T16:00:00',
        end: '2025-07-30T17:30:00',
        extendedProps: {
        department: 'BioChemistry',
      },
    },
    { 
        id: 'b',
        title: 'Patient Klaus Müller - Bauchschmerzen',
        start: '2025-07-27T10:10:00',
        end: '2025-07-27T12:15:00',
        color: "pink",
        extendedProps: {
        department: 'BioChemistry',
      }
    },
    
    ],
    eventDidMount: function(info) {
    console.log(info.event.extendedProps);
    // {description: "Lecture", department: "BioChemistry"}
  },
  eventClick: function(info) {
    eventData = info.event  
    eventState = true
    
  }
  });
</script>

<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/@event-calendar/build/dist/event-calendar.min.css"
/>


<div class="grid grid-cols-1 h-[92%] gap-1 2xl:grid-cols-12 2xl:grid-rows-1  ">

    <div class="{!eventState ? "col-span-12" : "col-span-8"}  min-h-0 bg-green-200 h-[100%] ">
        <div class="bg-blue-200 flex-1 min-h-0 h-[100%]">
            <!-- <button onclick={updateOptions}>Change slot duration</button> -->
            <Calendar plugins={[TimeGrid]} {options} />
          </div>
          
    </div>

    <div class="hidden {eventState && "col-span-4"}  {!eventState ? "hidden" : "2xl:block " } -blue-700 bg-orange-200  h-full  p-[1%]">
        
        <AgendaPatient eventData={eventData}/>
      
     
    </div>
 </div>


