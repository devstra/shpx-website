<script lang="ts">
  import ProductCard from "./ProductCard.svelte";
  import chair from "../assets/chair.png";
  import chair3 from "../assets/chair3.png";
  import chair2 from "../assets/chair2.png";
  import lamp from "../assets/lamp.png";
  import sofa from "../assets/sofa.png";
  import cabinet from "../assets/cabinet.png";
  import type { Product } from "src/types/Product.type";

  const products: Product[] = [
    { name: "Chaise Molle", price: 18, image: chair, category: "chair" },
    { name: "Chaise Molle", price: 18, image: chair3, category: "chair" },
    { name: "Chaise Molle", price: 18, image: lamp, category: "lamp" },
    { name: "Chaise Molle", price: 18, image: chair2, category: "chair" },
    { name: "Chaise Molle", price: 48, image: cabinet, category: "table" },
    { name: "Chaise Molle", price: 78, image: sofa, category: "sofa" },
  ];
  let selectedCategory = "all";
  $: filteredProducts =
    selectedCategory == "all"
      ? products
      : products.filter(p => p.category == selectedCategory);
</script>

<section>
  <h3>Products</h3>
  <div class="tabs">
    <button
      class:selected={selectedCategory == "all"}
      on:click={() => (selectedCategory = "all")}>All</button
    >
    <button
      class:selected={selectedCategory == "lamp"}
      on:click={() => (selectedCategory = "lamp")}>Lamp</button
    >
    <button
      class:selected={selectedCategory == "chair"}
      on:click={() => (selectedCategory = "chair")}>Chair</button
    >
    <button
      class:selected={selectedCategory == "table"}
      on:click={() => (selectedCategory = "table")}>Table</button
    >
    <button
      class:selected={selectedCategory == "sofa"}
      on:click={() => (selectedCategory = "sofa")}>Sofa</button
    >
  </div>
  <div class="grid">
    {#each filteredProducts as product}
      <ProductCard
        name={product.name}
        price={product.price}
        image={product.image}
        imageAlt="some description"
      />
    {/each}
  </div>
</section>

<style>
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-column-gap: 67px;
  }
  .tabs button {
    border: none;
    cursor: pointer;
    background-color: #fff;
    color: rgba(75, 75, 75, 0.5);
  }
  .selected {
    color: #000 !important;
  }
</style>
