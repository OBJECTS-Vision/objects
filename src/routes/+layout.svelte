<script>
  import { injectSpeedInsights } from "@vercel/speed-insights/sveltekit";
  import { inject } from "@vercel/analytics";
  import { page } from "$app/stores";
  import "./style.css";
  import Nav from "./Nav.svelte";
  import Footer from "./Footer.svelte";
  import Home from "./Home.svelte";
  import { get } from "svelte/store";

  // Vercel Perf widget
  injectSpeedInsights();
  //Vercel analytics
  inject();

  $: isRoot = $page.url.pathname === "/";
</script>

<div class="app" class:root={isRoot}>
  <div class="header">
    <Home />
    <Nav />
  </div>
  <div class="content">
    <slot />
  </div>

  <Footer />
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    padding: 1.6rem;
    box-sizing: border-box; /* Include padding in element's total height */
    position: absolute;
    inset: 0;
    @media screen and (min-width: 768px) {
      padding: 3rem;
    }
  }
  .app.root {
    background: repeating-radial-gradient(
      circle at 50% 50%,
      #8694a3 60%,
      rgba(196, 206, 241, 0.69) 90%,
      rgba(158, 189, 195, 0.75) 120%,
      #8694a3 160%
    );
  }
  .header {
    position: sticky;
    z-index: 10;
    justify-content: space-between;
    display: flex;
  }
  .content {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
  }
</style>
