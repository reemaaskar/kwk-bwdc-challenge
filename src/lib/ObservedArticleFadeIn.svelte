<script>
  import { onMount } from "svelte";

// Half used from the scrollytelling template, used video from "Effortlessly Create Scroll Animations with the Intersection Observer API"
export let children;
export let options = {
  threshold: [0.6],
};

  let visible = false;
  let uniqueId = Math.random().toString();

  onMount(() => {
    const observer = new IntersectionObserver((entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          visible = true;
          observer.unobserve(entry.target);
        }
      });
    }, options);

    const element = document.getElementById(uniqueId);
    if (element) observer.observe(element);
  });
</script>

<div id={uniqueId} class="article-text" class:visible>
  <p>{@render children()}</p>
</div>

<style>
  .article-text {
    margin: 50vh auto;
    width: 65%;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.4s ease 0.3s, transform 0.4s ease 0.3s;
    color: white;
    font-size: 1.25rem;
    line-height: 1.7;
  }

  .article-text.visible {
    opacity: 1;
    transform: translateY(0);
  }

</style>
