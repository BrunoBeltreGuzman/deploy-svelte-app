<!-- App.svelte -->
<script>
       import { Router, Link, Route } from "svelte-routing";
       import Index from "./pages/Index.svelte";
       import Home from "./pages/Home.svelte";
       import Fetch from "./pages/Fetch.svelte";
       import Ruta from "./pages/Ruta.svelte";
</script>

<main class="container">
       <Router>
              <nav class="navbar navbar-expand-lg navbar-light bg-light">
                     <div class="container-fluid">
                            <Link to="/" class="navbar-brand">
                                   <!-- svelte-ignore a11y-missing-attribute -->
                                   <img
                                          src="/favicon.png"
                                          width="25 px"
                                          height="25 px"
                                   />{" "}
                                   Svelte App</Link
                            >
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

                            <div
                                   class="collapse navbar-collapse"
                                   id="navbarSupportedContent"
                            >
                                   <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                                          <li class="nav-item">
                                                 <Link to="/" class="nav-link"
                                                        >Index</Link
                                                 >
                                          </li>

                                          <li class="nav-item">
                                                 <Link
                                                        to="/home"
                                                        class="nav-link"
                                                        >Home</Link
                                                 >
                                          </li>

                                          <li class="nav-item">
                                                 <Link
                                                        to="/fetch"
                                                        class="nav-link"
                                                        >Fetch</Link
                                                 >
                                          </li>

                                          <li class="nav-item">
                                                 <Link
                                                        to="/ruta/1"
                                                        class="nav-link"
                                                        >Ruta</Link
                                                 >
                                          </li>

                                          <ul />

                                          <div />
                                   </ul>
                            </div>
                     </div>
              </nav>

              <Route path="/" component={Index} />
              <Route path="/home" component={Home} />
              <Route path="/fetch" component={Fetch} />
              <Route path="/ruta/:id" let:params>
                     <Ruta id={params.id} />
              </Route>
       </Router>
</main>
