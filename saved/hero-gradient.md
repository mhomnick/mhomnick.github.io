# Animated Mesh Gradient Hero

## HTML — add inside `<section id="hero">` before `.hero-content`

```html
<div class="hero-blobs" aria-hidden="true">
  <div class="blob blob-1"></div>
  <div class="blob blob-2"></div>
  <div class="blob blob-3"></div>
  <div class="blob blob-4"></div>
</div>
```

## CSS — replace `#hero` block in style.css and add after it

```css
#hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 120px var(--pad-x) 96px;
  position: relative;
  overflow: hidden;
}

/* ---- Mesh gradient blobs ---- */
.hero-blobs {
  position: absolute;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(90px);
  opacity: 0.55;
  will-change: transform;
}

.blob-1 {
  width: 55vw;
  height: 55vw;
  background: radial-gradient(circle, rgba(20, 50, 160, 0.7), transparent 70%);
  top: -15%;
  left: -10%;
  animation: blobDrift1 18s ease-in-out infinite alternate;
}

.blob-2 {
  width: 45vw;
  height: 45vw;
  background: radial-gradient(circle, rgba(80, 15, 110, 0.6), transparent 70%);
  top: 10%;
  right: -5%;
  animation: blobDrift2 22s ease-in-out infinite alternate;
}

.blob-3 {
  width: 40vw;
  height: 40vw;
  background: radial-gradient(circle, rgba(8, 70, 100, 0.5), transparent 70%);
  bottom: -10%;
  left: 30%;
  animation: blobDrift3 16s ease-in-out infinite alternate;
}

.blob-4 {
  width: 30vw;
  height: 30vw;
  background: radial-gradient(circle, rgba(50, 10, 80, 0.45), transparent 70%);
  bottom: 20%;
  right: 20%;
  animation: blobDrift4 20s ease-in-out infinite alternate;
}

@keyframes blobDrift1 {
  0%   { transform: translate(0, 0) scale(1); }
  100% { transform: translate(8%, 12%) scale(1.1); }
}

@keyframes blobDrift2 {
  0%   { transform: translate(0, 0) scale(1); }
  100% { transform: translate(-10%, 8%) scale(0.95); }
}

@keyframes blobDrift3 {
  0%   { transform: translate(0, 0) scale(1); }
  100% { transform: translate(-8%, -10%) scale(1.08); }
}

@keyframes blobDrift4 {
  0%   { transform: translate(0, 0) scale(1); }
  100% { transform: translate(6%, -12%) scale(1.05); }
}

.hero-content {
  position: relative;
  z-index: 1;
}
```
