<script>
       import { onMount } from "svelte";

       //vars
       let data, loading, error;

       onMount(async () => {
              try {
                     loading = true;
                     const response = await fetch(
                            "https://jsonplaceholder.typicode.com/posts"
                     );
                     const json = await response.json();
                     console.log(json);
                     data = json;
                     loading = false;
              } catch (err) {
                     console.log(err);
                     loading = false;
                     error = err;
              }
       });
</script>

<main>
       <br />
       <br />
       <br />

       {#if data}
              <h1>Data:</h1>
              <br />
              <br />

              {#each data as row, index}
                     <pre
                            key={index}>
                     <p>
                            {JSON.stringify(row)}
                     </p>
              </pre>
              {/each}
       {/if}

       {#if loading == true}
              <h1>Loading...</h1>
       {/if}
</main>
