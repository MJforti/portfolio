# SYSTEM PROMPT: CINEMATIC PORTFOLIO GENERATOR

Task: Build single-file interactive portfolio web app with scroll-linked HD frame canvas.

## CONSTRAINTS & STACK
- Stack: HTML5, Vanilla CSS3, ES6+ JS. Zero external JS dependencies.
- Fonts: `DM Sans`, `DM Mono`, `Instrument Serif` (Google Fonts).
- Theme: Dark `#090a0f`, accent `#fa4f47` (red), `#9db9ff` (blue), glass `rgba(18,20,29,.46)` + `backdrop-filter: blur(18px)`.

## CANVAS SCROLL ENGINE
- Canvas: `<canvas id="scroll-video">` (fixed, inset 0, z-index -1).
- Sequence: 300 JPG frames (`./ezgif-1650ba708e34b86e-jpg/ezgif-frame-[001..300].jpg`).
- Quality: `dpr = min(window.devicePixelRatio || 1, 2.5)`, `imageSmoothingQuality = 'high'`, `zoom = 1.0`.
- Sync: `currentFrame = Math.floor((scrollY / maxScroll) * 299)`, throttle via `requestAnimationFrame`.

## LAYOUT & SECTIONS
1. Header: Glass navigation, brand `mj.`, links (`#about`, `#work`, `#journey`, `#contact`).
2. Hero: Headline `Building what moves people forward.`, status pill, video fallback.
3. About: Metrics grid (`15+` AI workflows, `80%` manual cut, `700+` mapped, `₹2.6L+` revenue).
4. Work: Bento grid (`xTag` AI Agent, `AgriConnect`, `Project Nirvi`, `Invoice Intelligence`).
5. Journey: Experience timeline & technical skill pills.
6. Contact: Centered glass card + email link (`workformj40@gmail.com`).

## PERF & ACCESSIBILITY
- Noise: SVG fractal noise overlay at `opacity: 0.025`.
- Motion: Respect `prefers-reduced-motion: reduce`.
- Responsive: CSS Grid + `clamp()` fluid typography.
