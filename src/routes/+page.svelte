<script>
  import { fade } from "svelte/transition";
  export let appName = "CubeIndex";
  const links = [
    { url: "https://cubeindex.netlify.app/", label: "CubeIndex" },
    { url: "https://cubeindexbeta.netlify.app/", label: "CubeIndex Beta" },
  ];
</script>

<svelte:head>
  <title>{appName} – We’ve moved</title>
  <meta
    name="description"
    content="{appName} has a new home. Visit our updated URLs."
  />
</svelte:head>

<main class="container" in:fade={{ duration: 400 }}>
  <img
    class="logo"
    src="/images/CubeIndex - Pixel Art.png"
    alt="{appName} logo"
  />
  <h1>We’ve moved!</h1>
  <p>{appName} is now available at:</p>

  <div class="links">
    {#each links as link}
      <a href={link.url} target="_blank" rel="noopener">{link.label}</a>
    {/each}
  </div>
</main>

<style>
  :global(html, body) {
    margin: 0;
    height: 100%;
    background: #000000; /* Black background */
  }

  .container {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: #000000; /* Black background */
    color: #ffffff; /* Primary color: white */
    text-align: center;
    padding: 1rem;
  }

  .logo {
    width: 200px;
    max-width: 80vw;
    border-radius: 0.75rem; /* Rounded corners */
    margin-bottom: 2rem;
  }

  h1 {
    font-size: 3rem; /* 48px */
    font-weight: 800;
    letter-spacing: -0.03em;
    margin: 0 0 1rem;
  }

  p {
    font-size: 1.25rem; /* 20px */
    margin: 0 0 2rem;
  }

  .links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 100%;
    max-width: 20rem;
  }

  .links a {
    display: block;
    width: 100%;
    padding: 1rem 1.5rem;
    border: 2px solid #ffffff; /* Primary color border */
    border-radius: 0.75rem;
    font-weight: 600;
    text-decoration: none;
    color: #ffffff; /* Primary color text */
    transition:
      background 0.15s ease,
      color 0.15s ease;
  }

  .links a:hover {
    background: #ffffff; /* Primary color background on hover */
    color: #000000; /* Black text on hover */
  }
</style>
