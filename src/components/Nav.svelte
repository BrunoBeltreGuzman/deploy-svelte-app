<!-- App.svelte -->
<script>
       import { Router, Link, Route } from "svelte-routing";
       import Index from "../pages/Index.svelte";
       import Home from "../pages/Home.svelte";
       import Fetch from "../pages/Fetch.svelte";
       import Ruta from "../pages/Ruta.svelte";
</script>

<main>
       <nav class="navbar navbar-expand-lg navbar-light bg-light">
              <div class="container-fluid">
                     <Link to="/" class="navbar-brand">Nextjs</Link>
                     <button
                            class="navbar-toggler"
                            type="button"
                            data-bs-toggle="collapse"
                            data-bs-target="#navbarSupportedContent"
                            aria-controls="navbarSupportedContent"
                            aria-expanded="false"
                            aria-label="Toggle navigation"
                     >
                            <span class="navbar-toggler-icon" />
                     </button>
                     <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                            <li class="nav-item">
                                   <Link href="/" class="nav-link">Index</Link>
                            </li>
                     </ul>
              </div>
       </nav>

       <Router>
              <nav>
                     <Link to="/">Index</Link>
                     <Link to="/home">Home</Link>
                     <Link to="/fetch">Fetch</Link>
                     <Link to="/ruta">Ruta</Link>
              </nav>

              <Route path="/">
                     <Index />
              </Route>
              <Route path="/home">
                     <Home />
              </Route>
              <Route path="/fetch">
                     <Fetch />
              </Route>
              <Route path="ruta">
                     <Ruta />
              </Route>
       </Router>
</main>
