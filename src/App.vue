<script setup>
import { ref } from 'vue'

const showGame = ref(false)

function playNow() {
  showGame.value = true
  requestAnimationFrame(() => {
    document.getElementById('game')?.scrollIntoView({ behavior: 'smooth' })
  })
}
</script>

<template>
  <header class="hero">
    <h1>Harry's Broom Ride</h1>
    <p class="tagline">A coin-collecting flight through an enchanted forest — built in Unity, shipped to the browser.</p>
    <button class="play-btn" @click="playNow">Play Now</button>
  </header>

  <section id="game" class="game-section" v-if="showGame">
    <iframe
      class="game-frame"
      src="/game/index.html"
      title="Harry's Broom Ride"
      allow="autoplay; fullscreen"
      allowfullscreen
    ></iframe>
    <p class="hint">Controls: A/D to turn, W/S to move, Space/Ctrl to rise/descend.</p>
  </section>

  <section class="about">
    <h2>About this project</h2>
    <p>
      A third-person flying game built in Unity 6 (URP), featuring procedural scene
      assembly, Cinemachine camera work, NPC wandering AI, and a coin-navigation
      compass HUD — then profiled and optimized before shipping as a WebGL build.
    </p>

    <h3>Tech stack</h3>
    <ul class="stack">
      <li>Unity 6 / C#</li>
      <li>Universal Render Pipeline (URP)</li>
      <li>Cinemachine</li>
      <li>Unity WebGL build</li>
      <li>Vue 3 + Vite</li>
      <li>Deployed on Vercel</li>
    </ul>
  </section>

  <footer>
    <a href="https://github.com/krngrover6/HarryRide" target="_blank" rel="noopener">Source on GitHub</a>
  </footer>
</template>

<style>
* { box-sizing: border-box; }

body {
  margin: 0;
  background: #0b0e14;
  color: #eae6d8;
  font-family: system-ui, -apple-system, sans-serif;
}

.hero {
  text-align: center;
  padding: 5rem 1.5rem 3rem;
}

.hero h1 {
  font-size: 2.75rem;
  margin: 0 0 0.75rem;
  color: #f4cc5a;
}

.tagline {
  color: #b9b3a0;
  max-width: 560px;
  margin: 0 auto 2rem;
  line-height: 1.5;
}

.play-btn {
  background: #6b1214;
  color: #f4cc5a;
  border: none;
  padding: 0.9rem 2.2rem;
  font-size: 1.1rem;
  font-weight: 600;
  border-radius: 6px;
  cursor: pointer;
}

.play-btn:hover {
  background: #841518;
}

.game-section {
  max-width: 960px;
  margin: 0 auto 3rem;
  padding: 0 1.5rem;
  text-align: center;
}

.game-frame {
  width: 100%;
  aspect-ratio: 16 / 9;
  border: 2px solid #2a2f3a;
  border-radius: 8px;
  background: #000;
}

.hint {
  color: #8b8574;
  font-size: 0.9rem;
  margin-top: 0.75rem;
}

.about {
  max-width: 680px;
  margin: 0 auto 3rem;
  padding: 0 1.5rem;
}

.about h2 {
  color: #f4cc5a;
}

.stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  list-style: none;
  padding: 0;
}

.stack li {
  background: #1b2028;
  border: 1px solid #2a2f3a;
  padding: 0.4rem 0.9rem;
  border-radius: 999px;
  font-size: 0.9rem;
}

footer {
  text-align: center;
  padding: 2rem 1rem 3rem;
}

footer a {
  color: #b9b3a0;
  text-decoration: none;
}

footer a:hover {
  color: #f4cc5a;
}
</style>
