<script lang="ts">
  export let name: string;
  export let price: number;
  export let image: string;
  export let imageAlt: string;
</script>

<div class="card">
  <h3>{name}</h3>
  <p>${price}</p>
  <img src={image} alt={imageAlt} />
</div>

<style>
  .card {
    background: #faf4ef;
    border-radius: 0px 0px 0px 50px;
  }
</style>
