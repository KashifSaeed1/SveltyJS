<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  const filter = (e) => {
    dispatch('filter', e.target.value);
  };
</script>

<div class="flex items-center mb-4">
  <p class="text-black mr-2">Filter User</p>
  <select class="text-black" name="user-filter" id="user-filter" on:change={filter}>
    <option value="all">All</option>
    <option value="active">Active</option>
    <option value="inActive">Inactive</option> 
  </select>
</div>
