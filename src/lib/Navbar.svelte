<script lang="ts">
  import logo from "../assets/logo.png";
  import cart from "../assets/cart.svg";
  import search from "../assets/search.svg";
</script>

<div>
  <img src={logo} alt="shpx logo" />
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Products</a>
    <a href="#">Contact</a>
  </nav>
  <span>
    <button><img src={search} alt="magnifying glass icon" /></button>
    <button><img src={cart} alt="shopping cart icon" /></button>
  </span>
</div>

<style>
  nav a {
    text-decoration: none;
    color: #000;
    /* margin-left: 16px; */
  }
  div {
    height: 126px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  button {
    width: 27px;
    height: 27px;
    border: none;
    background: none;
    cursor: pointer;
  }
  button:first-child {
    margin-right: 15px;
  }
</style>
