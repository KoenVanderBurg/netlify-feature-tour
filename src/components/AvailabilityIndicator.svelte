<!-- src/components/AvailabilityIndicator.svelte -->
<script>
  export let busyDays = [];
  let currentDate = new Date();
</script>

<div class="availability-indicator">
  {#each busyDays as busyDay}
    {#if busyDay === currentDate.toISOString().split('T')[0]}
      <div class="busy-day">Busy</div>
    {:else}
      <div class="free-day">Free</div>
    {/if}
  {/each}
</div>

<style>
  .availability-indicator {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .busy-day {
    background-color: red;
    color: white;
    padding: 4px;
    margin: 2px;
  }
  .free-day {
    background-color: green;
    color: white;
    padding: 4px;
    margin: 2px;
  }
</style>
