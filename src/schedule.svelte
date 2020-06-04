<script>
let schedule = [
  {
    time: "1am-2am",
    event: "Drink a lot of water",
  },
  {
    time: "2am-3:30am",
    event: "Watch anime with water and water",
  },
  {
    time: "3:30am-4am",
    event: "Play league of legend",
  }, 
  {
    time: "4am-5am",
    event: "Sleep zzz",
  }, 
  {
    time: "5am-6am",
    event: "Dreaming...what?? my program breaks again",
  }, 
];
</script>

<style>
table {
  color: #bbbbc4;
}

td, th {
  border-color: #555560;
}
/* change line color */
</style>

<schedule-table>
<!-- TODO update schedule (could use function loop to generate table entris here) -->
<table class="u-full-width">
  <thead>
    <tr>
      <th>Time</th>
      <th>Event</th>
    </tr>
  </thead>
  <tbody>
    {#each schedule as item}
      <tr>
        <td>{item.time}</td>
        <td>{item.event}</td>
      </tr>
    {/each}
  </tbody>
</table>


</schedule-table>