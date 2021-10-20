<script lang="ts">
  import leftArrow from "../assets/left-arrow.svg";
  import rightArrow from "../assets/right-arrow.svg";
  import livingRoom from "../assets/livingroom.png";
  import type { CarouselItem } from "../types/CarouselItem.type";

  const items: CarouselItem[] = [
    {
      title: "Showcase 1",
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. A, eleifend viverra nam libero tellus. Luctus ornare ac, dolor tempor pellentesque nec.",
      image: livingRoom,
    },
    {
      title: "Showcase 2",
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. A, eleifend viverra nam libero tellus. Luctus ornare ac, dolor tempor pellentesque nec.",
      image: livingRoom,
    },
    {
      title: "Showcase 3",
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. A, eleifend viverra nam libero tellus. Luctus ornare ac, dolor tempor pellentesque nec.",
      image: livingRoom,
    },
  ];
  let selectedItem: number = 0;

  function nextItem() {
    if (selectedItem < items.length - 1) {
      selectedItem++;
    }
  }
  function previousItem() {
    if (selectedItem > 0) {
      selectedItem--;
    }
  }
</script>

<section>
  <img class="image" src={items[selectedItem].image} alt="description here" />
  <div class="content">
    <h2>{items[selectedItem].title}</h2>
    <p>{items[selectedItem].text}</p>
    <div class="btn-row">
      <button
        on:click={previousItem}
        class:disabled={selectedItem == 0}
        disabled={selectedItem == 0}
        ><img src={leftArrow} alt="left arrow" /></button
      >
      <button
        on:click={nextItem}
        class:disabled={selectedItem == items.length - 1}
        disabled={selectedItem == items.length - 1}
        ><img src={rightArrow} alt="right arrow" /></button
      >
    </div>
  </div>
</section>

<style>
  section {
    display: flex;
    flex-direction: row;
  }
  .content {
    display: flex;
    flex-direction: column;
  }
  .btn-row {
    display: flex;
    flex-direction: row;
  }
  .image {
    border-radius: 0px 0px 0px 100px;
  }
  button {
    background: #faf4ef;
    border: none;
    width: 70px;
    height: 70px;
    cursor: pointer;
  }
  .btn-row > button {
    margin-right: 12px;
  }
  .disabled {
    opacity: 0.5;
  }
</style>
