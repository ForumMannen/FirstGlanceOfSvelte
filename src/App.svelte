<script>
  // Add the import and component, LAST.
  // import Pointer from "./lib/Pointer.svelte";

  // SIMPLE COUNTER
  let counter = 0;
  $: doubled = counter * 2;

  function increment() {
    counter += 1;
  }

  $: {
    console.log(counter);
    if (counter > 10) alert("BIG BOY!");
  }

  // PUSHING TO ARRAY FROM FUNCTION
  let frameworks = ["React", "Vue", "Svelte", "Angular"];

  $: {
    console.log(frameworks);
  }

  function addFramework() {
    frameworks = [...frameworks, "Another Framework"];
  }

  // LOOP THROUGH ARRAY WITH OBJECTS
  const users = [
    { name: "Star-Lord", id: crypto.randomUUID() },
    { name: "Rocket", id: crypto.randomUUID() },
    { name: "Yondu", id: crypto.randomUUID() },
  ];

  // IF STATEMENT LOGIN
  let user = null;
</script>

<!-- <Pointer /> -->

<!--SIMPLE COUNTER-->
<h2>Doubled: {doubled}</h2>
<h2>Single: {counter}</h2>
<button on:click={increment}>Increment</button>
<button on:click={() => (counter -= 1)}>Decrement</button>

<!--PUSHING TO ARRAY FROM FUNCTION -->
<h2>Add new Framework</h2>
<button on:click={addFramework}>Add new Framework</button>

<!--LOOP THROUGH ARRAY WITH OBJECTS-->
{#each users as user (user.id)}
  <div>
    <h2>{user.name}</h2>
    <p>{user.id}</p>
  </div>
{/each}

<!--IF STATEMENT LOGIN-->
<button on:click={() => (user = !user)}>Sign in</button>

{#if !user}
  <h1>Please sign in!</h1>
{:else}
  <h1>Welcome ForumMannen!</h1>
{/if}
