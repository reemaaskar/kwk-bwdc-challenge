<script>
  import { onMount } from "svelte";

  let showH1 = false;
  let showH2 = false;
  let showH3 = false;

  let h2Ref, h3Ref;

  // Observe scroll into view
  onMount(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) showH2 = true;
      },
      { threshold: 0.4 }
    );
    if (h2Ref) observer.observe(h2Ref);

    const observer3 = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) showH3 = true;
      },
      { threshold: 0.5 }
    );
    if (h3Ref) observer3.observe(h3Ref);
  });

  // H1 fades in immediately after mount
  onMount(() => {
    setTimeout(() => (showH1 = true), 200);
  });
</script>

<section class="SectionOne">
  <div class="background"></div>
  <div class="overlay-text">
    <h1 class:h1-visible={showH1}>THE DIGITAL DIVIDE</h1>
    <h2 bind:this={h2Ref} class:h2-visible={showH2}>
      Is it truly black and white?
    </h2>
    <div class="arrow" class:bounce={showH2}>↓</div>
    <h3 bind:this={h3Ref} class:h3-visible={showH3}>
      WHAT WOULD BRIDGING THE DIGITAL DIVIDE<br />
      UNLOCK FOR BLACK WEALTH EQUITY?
    </h3>
  </div>
</section>

<style>
  .SectionOne {
    position: relative;
    height: 100vh;
    overflow: hidden;
  }

  .background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-image: url("/public/Intro Image.png");
    background-size: cover;
    background-position: center;
    z-index: -1;
  }

  .overlay-text {
    position: relative;
    padding: 20vh 5vw;
    color: white;
    text-align: center;
    z-index: 1;
  }

  h1,
  h2,
  h3,
  .arrow {
    opacity: 0;
    transition:
      opacity 1s ease,
      transform 1s ease;
    transform: translateY(20px);
  }

  .h1-visible {
    opacity: 1;
    transform: translateY(0);
  }

  .h2-visible {
    opacity: 1;
    transform: translateY(0);
  }

  .h3-visible {
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
