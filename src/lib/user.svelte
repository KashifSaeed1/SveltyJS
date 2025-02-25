
<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();
  export let userImage;
  export let userName;
  export let userEmail;
  export let index;
  export let user;

  const remove = () => {
    dispatch('remove', user.id);
  };
</script>

<div class="relative flex items-center p-4 bg-white rounded-lg shadow-md space-x-4 border border-gray-200">
    <div on:click={remove} class="absolute top-2 right-2 text-gray-600 cursor-pointer hover:text-red-500">
        X
    </div>
    <p class="text-lg font-semibold text-gray-700">{index + 1}</p>
    <img src="{userImage}" alt="User Image" class="w-12 h-12 rounded-full border border-gray-300">
    <div>
        <p class="text-gray-800 font-medium">{userName}</p>
        <p class="text-gray-500 text-sm">{userEmail}</p>
    </div>
</div>
