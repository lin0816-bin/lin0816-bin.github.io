<template>
  <div class="home">
    <!-- ===== Particle Canvas ===== -->
    <canvas ref="particleCanvas" class="particles"></canvas>

    <!-- ===== Hero Section ===== -->
    <section class="hero">
      <div class="avatar-wrapper animate-in" style="animation-delay: 0.1s">
        <div class="avatar-ring"></div>
        <img
          class="avatar"
          src="https://github.com/lin0816-bin.png"
          alt="avatar"
          @error="onAvatarError"
        />
      </div>

      <h1 class="hero-title animate-in" style="animation-delay: 0.3s">
        <span class="glitch-text" data-text="Lin0816">Lin0816</span>
      </h1>

      <div class="typewriter-wrap animate-in" style="animation-delay: 0.5s">
        <span class="prompt">&gt;</span>
        <span class="typewriter">{{ displayedText }}</span>
        <span class="typewriter-cursor">|</span>
      </div>

      <p class="hero-bio animate-in" style="animation-delay: 0.7s">
        Full-Stack Developer &nbsp;·&nbsp; Open Source Enthusiast &nbsp;·&nbsp; Lifelong Learner
      </p>

      <!-- Mini Stats Row -->
      <div class="mini-stats animate-in" style="animation-delay: 0.9s">
        <div class="mini-stat">
          <span class="mini-stat-num">10+</span>
          <span class="mini-stat-label">Repos</span>
        </div>
        <div class="mini-stat-divider"></div>
        <div class="mini-stat">
          <span class="mini-stat-num">⭐</span>
          <span class="mini-stat-label">Stars</span>
        </div>
        <div class="mini-stat-divider"></div>
        <div class="mini-stat">
          <span class="mini-stat-num">&lt;/&gt;</span>
          <span class="mini-stat-label">Code</span>
        </div>
      </div>

      <!-- Social Links -->
      <div class="social-links animate-in" style="animation-delay: 1.0s">
        <a href="https://github.com/lin0816-bin" target="_blank" class="social-btn" title="GitHub">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.387.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.73.083-.73 1.205.085 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.605-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 21.795 24 17.295 24 12c0-6.63-5.37-12-12-12z"/></svg>
        </a>
        <a href="mailto:lin0816@example.com" class="social-btn" title="Email">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        </a>
      </div>

      <!-- Scroll hint -->
      <div class="scroll-hint animate-in" style="animation-delay: 1.5s">
        <div class="scroll-mouse">
          <div class="scroll-dot"></div>
        </div>
        <span class="scroll-text">SCROLL</span>
      </div>
    </section>

    <!-- ===== GitHub Stats ===== -->
    <section id="stats" class="section">
      <h2 class="section-title animate-in">
        <span class="section-icon">◈</span> GitHub 统计
        <span class="section-line"></span>
      </h2>
      <div class="stats-grid">
        <div class="card animate-in" style="animation-delay: 0.1s">
          <div class="card-header">
            <span class="card-dot"></span>
            <span class="card-label">Overview</span>
          </div>
          <img
            class="stats-img"
            src="https://github-readme-stats.vercel.app/api?username=lin0816-bin&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00f0ff&icon_color=ff2d95&text_color=8b8fa3&ring_color=00f0ff&border_radius=12"
            alt="GitHub Stats"
            loading="lazy"
          />
        </div>
        <div class="card animate-in" style="animation-delay: 0.2s">
          <div class="card-header">
            <span class="card-dot green"></span>
            <span class="card-label">Top Languages</span>
          </div>
          <img
            class="stats-img"
            src="https://github-readme-stats.vercel.app/api/top-langs/?username=lin0816-bin&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00f0ff&text_color=8b8fa3&border_radius=12"
            alt="Top Languages"
            loading="lazy"
          />
        </div>
      </div>
    </section>

    <!-- ===== Activity Graph ===== -->
    <section class="section">
      <div class="card animate-in full-width">
        <div class="card-header">
          <span class="card-dot yellow"></span>
          <span class="card-label">Contribution Activity</span>
        </div>
        <img
          class="stats-img"
          src="https://github-readme-activity-graph.vercel.app/graph?username=lin0816-bin&theme=tokyo-night&hide_border=true&bg_color=0d0d1a&color=00f0ff&line=ff2d95&point=00f0ff&area=true&area_color=rgba(0,240,255,0.08)&radius=12"
          alt="Activity Graph"
          loading="lazy"
        />
      </div>
    </section>

    <!-- ===== Skills ===== -->
    <section id="skills" class="section">
      <h2 class="section-title animate-in">
        <span class="section-icon">◆</span> 技术栈
        <span class="section-line"></span>
      </h2>
      <div class="skills-container">
        <div
          v-for="(group, idx) in skillGroups"
          :key="group.category"
          class="skill-group animate-in"
          :style="{ animationDelay: `${0.1 * (idx + 1)}s` }"
        >
          <h3 class="skill-category">{{ group.category }}</h3>
          <div class="badge-cloud">
            <span
              v-for="badge in group.badges"
              :key="badge.name"
              class="badge"
            >
              <span class="badge-icon">{{ badge.icon }}</span>
              {{ badge.name }}
            </span>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== Footer ===== -->
    <footer class="footer">
      <div class="footer-divider"></div>
      <p class="footer-text">
        Built with <span class="heart">&#9829;</span> by <span class="cyan">Lin0816</span>
      </p>
      <p class="footer-sub">&copy; {{ currentYear }} · All Rights Reserved</p>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentYear = new Date().getFullYear()

// ===== Typing Effect =====
const fullText = 'echo "Hello, World! Welcome to my digital space."'
const displayedText = ref('')
let typeIndex = 0
let typeTimer = null
let typePaused = false

function startTyping() {
  typeTimer = setInterval(() => {
    if (typeIndex < fullText.length) {
      displayedText.value = fullText.slice(0, typeIndex + 1)
      typeIndex++
    } else {
      clearInterval(typeTimer)
      // Pause at end, then restart after delay
      setTimeout(() => {
        displayedText.value = ''
        typeIndex = 0
        startTyping()
      }, 3000)
    }
  }, 60)
}

// ===== Avatar Fallback =====
function onAvatarError(e) {
  e.target.style.display = 'none'
}

// ===== Particle System =====
const particleCanvas = ref(null)
let animationId = null

function initParticles() {
  const canvas = particleCanvas.value
  if (!canvas) return
  const ctx = canvas.getContext('2d')
  let particles = []

  function resize() {
    canvas.width = window.innerWidth
    canvas.height = window.innerHeight
  }
  resize()
  window.addEventListener('resize', resize)

  const count = 80
  for (let i = 0; i < count; i++) {
    particles.push({
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      r: Math.random() * 2 + 0.5,
      dx: (Math.random() - 0.5) * 0.5,
      dy: (Math.random() - 0.5) * 0.5,
      alpha: Math.random() * 0.5 + 0.2,
      alphaDir: Math.random() > 0.5 ? 0.002 : -0.002,
    })
  }

  function animate() {
    ctx.clearRect(0, 0, canvas.width, canvas.height)

    for (const p of particles) {
      p.x += p.dx
      p.y += p.dy
      p.alpha += p.alphaDir
      if (p.alpha >= 0.7 || p.alpha <= 0.1) p.alphaDir *= -1

      // Wrap around
      if (p.x < -10) p.x = canvas.width + 10
      if (p.x > canvas.width + 10) p.x = -10
      if (p.y < -10) p.y = canvas.height + 10
      if (p.y > canvas.height + 10) p.y = -10

      ctx.beginPath()
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2)
      ctx.fillStyle = `rgba(0, 240, 255, ${p.alpha})`
      ctx.fill()
    }

    // Draw connections
    for (let i = 0; i < particles.length; i++) {
      for (let j = i + 1; j < particles.length; j++) {
        const dx = particles[i].x - particles[j].x
        const dy = particles[i].y - particles[j].y
        const dist = Math.sqrt(dx * dx + dy * dy)
        if (dist < 120) {
          ctx.beginPath()
          ctx.moveTo(particles[i].x, particles[i].y)
          ctx.lineTo(particles[j].x, particles[j].y)
          ctx.strokeStyle = `rgba(0, 240, 255, ${0.06 * (1 - dist / 120)})`
          ctx.lineWidth = 0.5
          ctx.stroke()
        }
      }
    }

    animationId = requestAnimationFrame(animate)
  }

  animate()
}

// ===== Skill Groups =====
const skillGroups = [
  {
    category: 'Languages',
    badges: [
      { name: 'JavaScript', icon: '⬡' },
      { name: 'TypeScript', icon: '⬢' },
      { name: 'Python', icon: '🐍' },
      { name: 'Java', icon: '☕' },
      { name: 'HTML5', icon: '⬟' },
      { name: 'CSS3', icon: '⬠' },
    ],
  },
  {
    category: 'Frameworks',
    badges: [
      { name: 'Vue.js', icon: '△' },
      { name: 'React', icon: '⚛' },
      { name: 'Node.js', icon: '⊳' },
      { name: 'Spring', icon: '🍃' },
      { name: 'Flask', icon: '🔥' },
    ],
  },
  {
    category: 'Tools & Others',
    badges: [
      { name: 'Git', icon: '⎔' },
      { name: 'Docker', icon: '🐋' },
      { name: 'Linux', icon: '🐧' },
      { name: 'VS Code', icon: '◧' },
      { name: 'MySQL', icon: '🗄' },
      { name: 'MongoDB', icon: '🍃' },
    ],
  },
]

onMounted(() => {
  startTyping()
  initParticles()
})

onUnmounted(() => {
  clearInterval(typeTimer)
  if (animationId) cancelAnimationFrame(animationId)
})
</script>

<style scoped>
/* ===== Particles ===== */
.particles {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}

/* ===== Layout ===== */
.home {
  position: relative;
  z-index: 1;
}

.section {
  max-width: 1000px;
  margin: 0 auto;
  padding: 4rem 1.5rem;
}

/* ===== Hero ===== */
.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  text-align: center;
  padding: 2rem 1.5rem 4rem;
  position: relative;
}

.avatar-wrapper {
  position: relative;
  margin-bottom: 2rem;
  animation: float 4s ease-in-out infinite;
}

.avatar-ring {
  position: absolute;
  inset: -4px;
  border-radius: 50%;
  background: conic-gradient(from 0deg, var(--cyan), var(--magenta), var(--cyan));
  animation: spin 4s linear infinite;
  opacity: 0.6;
}

@keyframes spin {
  100% { transform: rotate(360deg); }
}

.avatar {
  width: 110px;
  height: 110px;
  border-radius: 50%;
  border: 3px solid var(--bg-deep);
  position: relative;
  z-index: 1;
  display: block;
  object-fit: cover;
  background: var(--bg-card);
}

.hero-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: clamp(2.5rem, 6vw, 4rem);
  font-weight: 700;
  margin-bottom: 1rem;
  line-height: 1.1;
}

.glitch-text {
  position: relative;
  background: linear-gradient(135deg, var(--cyan) 0%, var(--magenta) 50%, var(--cyan) 100%);
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: textShimmer 3s linear infinite;
}

.typewriter-wrap {
  display: flex;
  align-items: center;
  gap: 0;
  font-family: 'JetBrains Mono', monospace;
  font-size: 1rem;
  margin-bottom: 1.5rem;
  height: 1.8em;
}

.prompt {
  color: var(--green);
  margin-right: 0.5rem;
  user-select: none;
}

.typewriter {
  color: var(--text-secondary);
}

.typewriter-cursor {
  color: var(--cyan);
  animation: blink 1s step-end infinite;
  font-weight: 100;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.hero-bio {
  font-size: 1.05rem;
  color: var(--text-secondary);
  margin-bottom: 2rem;
  letter-spacing: 0.5px;
}

/* Mini Stats */
.mini-stats {
  display: flex;
  align-items: center;
  gap: 2rem;
  margin-bottom: 2rem;
  padding: 0.8rem 2.5rem;
  background: var(--bg-card);
  border: 1px solid var(--border-glow);
  border-radius: 50px;
}

.mini-stat {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
}

.mini-stat-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--cyan);
}

.mini-stat-label {
  font-size: 0.7rem;
  color: var(--text-dim);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.mini-stat-divider {
  width: 1px;
  height: 30px;
  background: var(--border-glow);
}

/* Social Buttons */
.social-links {
  display: flex;
  gap: 1rem;
  margin-bottom: 3rem;
}

.social-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: 1px solid var(--border-glow);
  color: var(--text-secondary);
  transition: all var(--transition);
  background: var(--bg-card);
}

.social-btn:hover {
  color: var(--cyan);
  border-color: var(--cyan);
  box-shadow: 0 0 20px var(--cyan-dim);
  transform: translateY(-2px);
}

/* Scroll Hint */
.scroll-hint {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  position: absolute;
  bottom: 2rem;
}

.scroll-mouse {
  width: 24px;
  height: 38px;
  border: 2px solid var(--text-dim);
  border-radius: 12px;
  position: relative;
}

.scroll-dot {
  width: 4px;
  height: 8px;
  background: var(--cyan);
  border-radius: 2px;
  position: absolute;
  top: 6px;
  left: 50%;
  transform: translateX(-50%);
  animation: scrollAnim 2s ease-in-out infinite;
}

@keyframes scrollAnim {
  0%, 100% { opacity: 1; top: 6px; }
  50% { opacity: 0.3; top: 16px; }
}

.scroll-text {
  font-size: 0.6rem;
  color: var(--text-dim);
  letter-spacing: 3px;
}

/* ===== Section Title ===== */
.section-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--text-primary);
  display: flex;
  align-items: center;
  gap: 0.6rem;
  margin-bottom: 2rem;
}

.section-icon {
  color: var(--cyan);
  font-size: 1rem;
}

.section-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, var(--border-glow), transparent);
  margin-left: 0.5rem;
}

/* ===== Cards ===== */
.card {
  background: var(--bg-card);
  border: 1px solid var(--border-glow);
  border-radius: var(--radius);
  padding: 1.5rem;
  transition: all var(--transition);
  position: relative;
  overflow: hidden;
}

.card::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: var(--radius);
  padding: 1px;
  background: linear-gradient(135deg, transparent 40%, rgba(0, 240, 255, 0.1), transparent 60%);
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  pointer-events: none;
}

.card:hover {
  border-color: var(--border-strong);
  box-shadow: 0 0 30px var(--cyan-dim), 0 8px 32px rgba(0, 0, 0, 0.4);
  transform: translateY(-2px);
}

.card-header {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid var(--border-glow);
}

.card-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--cyan);
  box-shadow: 0 0 8px var(--cyan);
}

.card-dot.green { background: var(--green); box-shadow: 0 0 8px var(--green); }
.card-dot.yellow { background: var(--yellow); box-shadow: 0 0 8px var(--yellow); }

.card-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.8rem;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.stats-img {
  width: 100%;
  display: block;
  border-radius: 8px;
}

.full-width {
  grid-column: 1 / -1;
}

/* Stats Grid */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
}

@media (max-width: 700px) {
  .stats-grid {
    grid-template-columns: 1fr;
  }
}

/* ===== Skills ===== */
.skills-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.skill-group {
  background: var(--bg-card);
  border: 1px solid var(--border-glow);
  border-radius: var(--radius);
  padding: 1.5rem;
  transition: all var(--transition);
}

.skill-group:hover {
  border-color: var(--border-strong);
  box-shadow: 0 0 20px rgba(255, 45, 149, 0.1);
}

.skill-category {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.85rem;
  color: var(--magenta);
  margin-bottom: 1rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.badge-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  padding: 0.4rem 1rem;
  background: rgba(0, 240, 255, 0.05);
  border: 1px solid var(--border-glow);
  border-radius: 50px;
  font-size: 0.85rem;
  color: var(--text-secondary);
  font-family: 'JetBrains Mono', monospace;
  transition: all var(--transition);
  cursor: default;
}

.badge:hover {
  background: var(--cyan-dim);
  border-color: var(--cyan);
  color: var(--cyan);
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 240, 255, 0.15);
}

.badge-icon {
  font-size: 0.9rem;
}

/* ===== Footer ===== */
.footer {
  text-align: center;
  padding: 3rem 1.5rem;
  position: relative;
}

.footer-divider {
  width: 60px;
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--cyan), transparent);
  margin: 0 auto 1.5rem;
}

.footer-text {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.85rem;
  color: var(--text-secondary);
  margin-bottom: 0.3rem;
}

.heart {
  color: var(--magenta);
  display: inline-block;
  animation: float 1.5s ease-in-out infinite;
}

.cyan {
  color: var(--cyan);
}

.footer-sub {
  font-size: 0.7rem;
  color: var(--text-dim);
  font-family: 'JetBrains Mono', monospace;
}
</style>
