<template>
  <nav>
    <div class="nav-inner">
      <router-link to="/" class="logo">
        <span class="bracket">[</span>Lin0816<span class="bracket">]</span>
        <span class="cursor">_</span>
      </router-link>
      <div class="nav-links">
        <a href="#stats" class="nav-link">
          <span class="nav-icon">◈</span> 统计
        </a>
        <a href="#skills" class="nav-link">
          <span class="nav-icon">◆</span> 技能
        </a>
        <a href="https://github.com/lin0816-bin" target="_blank" class="nav-link external">
          <span class="nav-icon">⎔</span> GitHub
        </a>
      </div>
    </div>
  </nav>
</template>

<script setup>
</script>

<style scoped>
nav {
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 1px solid var(--border-glow);
  background: rgba(6, 6, 12, 0.85);
  backdrop-filter: blur(20px) saturate(180%);
}

.nav-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
  height: 60px;
  max-width: 1200px;
  margin: 0 auto;
}

.logo {
  font-family: 'JetBrains Mono', monospace;
  font-weight: 700;
  font-size: 1.15rem;
  color: var(--text-primary);
  letter-spacing: 1px;
  display: flex;
  align-items: center;
  gap: 1px;
}

.logo .bracket {
  color: var(--cyan);
  font-weight: 300;
}

.cursor {
  color: var(--cyan);
  animation: blink 1s step-end infinite;
  margin-left: 2px;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.nav-links {
  display: flex;
  gap: 0.25rem;
}

.nav-link {
  color: var(--text-secondary);
  padding: 0.4rem 1rem;
  border-radius: 8px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: all var(--transition);
  border: 1px solid transparent;
  display: flex;
  align-items: center;
  gap: 4px;
}

.nav-link:hover {
  color: var(--cyan);
  background: var(--cyan-dim);
  border-color: var(--border-glow);
}

.nav-icon {
  font-size: 0.7rem;
  color: var(--cyan);
  opacity: 0.7;
}

.nav-link.external::after {
  content: ' ↗';
  font-size: 0.7rem;
  opacity: 0.5;
  margin-left: 2px;
}
</style>
