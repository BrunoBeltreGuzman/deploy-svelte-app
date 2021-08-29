<script>
       export let id;

       import { onMount } from "svelte";

       //vars
       let data, loading, error;
       let isValidateId = false;

       onMount(async () => {
              //Validate id
              if (id) {
                     try {
                            id = parseInt(id);
                     } catch (err) {
                            isValidateId = false;
                     }
                     if (id > 0) {
                            isValidateId = true;
                     }
              } else {
                     isValidateId = false;
                     loading = false;
                     return;
              }

              try {
                     loading = true;
                     const response = await fetch(
                            "https://jsonplaceholder.typicode.com/posts/" + id
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
       {#if id}
              {#if id > 0}
                     <h1>Parameters: {id}</h1>
                     <br />

                     {#if data}
                            <h1>Data:</h1>
                            <br />
                            <br />

                            <pre>
                                   <p>
                                          {JSON.stringify(data)}
                                   </p>
                            </pre>
                     {/if}
              {:else}
                     <h1>Invalid Parameters</h1>
              {/if}
       {:else}
              <h1>Invalid Parameters</h1>
       {/if}

       {#if loading == true}
              <h1>Loading...</h1>
       {/if}
</main>
