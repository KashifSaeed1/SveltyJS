<script>
  export let userImage;
  export let userName;
  export let userEmail;
  export let index;
</script>

<div class="flex items-center p-4 bg-white rounded-lg shadow-md space-x-4 border border-gray-200">
  <p class="text-lg font-semibold text-gray-700">{index + 1}</p>
  <img src="{userImage}" alt="User Image" class="w-12 h-12 rounded-full border border-gray-300">
  <div>
    <p class="text-gray-800 font-medium">{userName}</p>
    <p class="text-gray-500 text-sm">{userEmail}</p>
  </div>
</div>
