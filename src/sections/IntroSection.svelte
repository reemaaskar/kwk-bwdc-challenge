<script>
  import { onMount } from "svelte";

  let showH1 = false;
  let showH2 = false;
  let triggerRef;

  // Observe scroll into view
  onMount(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) {
          showH1 = true;
          setTimeout(() => {
            showH2 = true;
          }, 1000);
        }
      },
      { threshold: 0.5 }
    );

    if (triggerRef) observer.observe(triggerRef);
  });
</script>

<section class="SectionOne">
  <div class="background"></div>
  <div class="overlay-text" bind:this={triggerRef}>
    <h1 class:h1-visible={showH1}>THE DIGITAL DIVIDE</h1>
    <h2 class:h2-visible={showH2}>Is it truly Black and White?</h2>
    <div class="arrow" class:bounce={showH2}>
      <img src="public\arrow.png" alt="arrow" />
    </div>
  </div>
</section>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Cal+Sans&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Raleway:ital,wght@0,100..900;1,100..900&display=swap");
  @import url("https://fonts.cdnfonts.com/css/safira-march-personal-use");

  .SectionOne {
    position: relative;
    height: 150vh;
    overflow: hidden;
  }

  .background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-image: url("/public/Into Image.jpg");
    background-size: cover;
    background-position: center;
    z-index: -1;
  }

  .background::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0.3),
      rgba(0, 0, 0, 1)
    );
    z-index: 1;
  }
  .overlay-text {
    position: relative;
    padding: 45vh 5vw;
    color: white;
    text-align: center;
    z-index: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
  }

  h1 {
    font-family: "Cal Sans", sans-serif;
    font-weight: 400;
    font-style: normal;
    font-size: 75px;
    margin-bottom: 0.4rem;
  }

  h2 {
    font-family: "Safira March Personal Use", sans-serif;
    font-weight: 300;
    font-style: normal;
    font-size: 25px;
    margin-top: 0;
  }

  h1,
  h2 {
    opacity: 0;
    transition:
      opacity 1s ease,
      transform 1s ease;
    transform: translateY(20px);
  }
  .arrow img {
    margin-top: 10rem;
    position: center;
    width: 5%;
  }
  .h1-visible {
    opacity: 1;
    transform: translateY(0);
  }

  .h2-visible {
    opacity: 1;
    transform: translateY(0);
  }

  .arrow.bounce {
    animation: bounce 2s infinite;
  }

  @keyframes bounce {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(8px);
    }
  }
</style>
