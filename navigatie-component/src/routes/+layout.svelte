<script>
  import Header from "$lib/Components/Header.svelte";
  import Footer from "$lib/Components/Footer.svelte";
  import { page } from "$app/stores";
  import Nav from "../lib/components/nav.svelte";
</script>

<Header path={$page.url.pathname} />

<slot />
<Nav />

<Footer />
