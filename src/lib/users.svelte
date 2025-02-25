<script>
  import User from "./user.svelte";

  let users = [
    { id: 1, userImage: "image1.jpg", userName: "John Doe", userEmail: "john@example.com", active: "active" },
    { id: 2, userImage: "image2.jpg", userName: "Jane Smith", userEmail: "jane@example.com", active: "inActive" },
    { id: 3, userImage: "image3.jpg", userName: "Mike Johnson", userEmail: "mike@example.com", active: "active" }
  ]; 

  let filterUsers = [...users]; 

  const filter = (e) => {
    const status = e.target.value;
    if (status === "all") {
      filterUsers = [...users]; 
    } else {
      filterUsers = users.filter((user) => user.active === status);
    }
  };
</script>

<div class="flex flex-col items-center p-6 bg-gray-100 min-h-screen">
  <h1 class="text-red-500 text-2xl font-bold mb-4">List of Users</h1>
  
  <div class="flex items-center mb-4">
    <p class="text-black mr-2">Filter User</p>
    <select class="text-black" name="user-filter" id="user-filter" on:change={filter}>
      <option value="all">All</option>
      <option value="active">Active</option>
      <option value="inActive">InActive</option>
    </select>
  </div>
  
  <div class="w-full max-w-md space-y-4">
    {#each filterUsers as user, i (user.id)}
      <User
        userImage={user.userImage} 
        userName={user.userName} 
        userEmail={user.userEmail} 
        index={i} 
      />
    {:else}
      <p class="text-gray-600 text-center">No users found</p>
    {/each}
  </div>
</div>
