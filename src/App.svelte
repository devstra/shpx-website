<script lang="ts">
  import Footer from "./lib/Footer.svelte";
  import Carousel from "./lib/Carousel.svelte";
  import ProductGrid from "./lib/ProductGrid.svelte";
  import Navbar from "./lib/Navbar.svelte";
  import LandingSection from "./lib/LandingSection.svelte";
</script>

<main>
  <Navbar />
  <LandingSection />
  <ProductGrid />
  <Carousel />
  <Footer />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
