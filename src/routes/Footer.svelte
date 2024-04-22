<script>
  import Instagram from "$lib/components/icons/Instagram.svelte";
  import Tiktok from "$lib/components/icons/Tiktok.svelte";
  import X from "$lib/components/icons/X.svelte";
  import { page } from "$app/stores";
</script>

<div class="content" class:justify-end={$page.url.pathname === "/"} class:justify-space-between={$page.url.pathname !== "/"}>
  {#if $page.url.pathname !== "/"}
    <span class="copyright"><h2>© 2024 OBJECTS</h2></span>
  {/if}
  <span class="icon-links">
    <a
      class="icon-link"
      href="https://instagram.com/objects.ig"
      target="_blank"
      rel="noopener noreferrer"
    >
      <Instagram /></a
    >
    <a
      class="icon-link"
      href="https://x.com/objectsvision"
      target="_blank"
      rel="noopener noreferrer"
    >
      <X /></a
    ><a
      class="icon-link"
      href="https://tiktok.com/@objects.tok"
      target="_blank"
      rel="noopener noreferrer"
    >
      <Tiktok />
    </a></span
  >
</div>

<style>
  .content {
    display: flex;
    align-items: baseline;
  }
  .justify-end {
    justify-content: flex-end;
  }
  .justify-space-between {
    justify-content: space-between;
  }
  .icon-links {
    display: flex;
    gap: 0.5rem;
  }

  .icon-link {
    color: rgba(0, 0, 0, 0.6);
  }

  h2 {
    font-size: small;
    letter-spacing: 0;
  }
</style>
