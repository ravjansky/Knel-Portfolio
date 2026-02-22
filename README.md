# Architect of Seconds | Knel Elgincolin's Portfolio

A high-performance, cinematic, single-page portfolio designed for Knel Elgincolin, a Creative Director and Senior Video Editor specializing in retention engineering and viral pacing.

The website delivers an immersive front-end experience using cutting-edge WebGL, physics simulations, and buttery smooth scroll animations while maintaining pristine performance and a premium brutalist-sleek design language.

## 🚀 Key Features

*   **Preloader Mask Zoom:** A cinematic entrance that hooks the viewer instantly as the custom logo draws its strokes, zooms significantly, and dives seamlessly into the hero section.
*   **Fluid Layouts:** Uses modern CSS Grid and Flexbox for exact stylistic positioning ("ladder/staircase" typography layout).
*   **WebGL Hero Gradient:** A constantly shifting, liquid-like, interactive Three.js gradient mapping to color tokens perfectly mimicking background blobs in motion.
*   **3D Scrolling WebGL Gallery:** A custom WebGL perspective gallery built natively in Three.js, scrubbed and mathematically driven by page scroll, flawlessly scaling across window sizes and halting cleanly at the final iteration of the frame.
*   **Micro-interactions:** Interactive hover states, smooth GSAP sequences, and buttery CSS hardware-accelerated transforms.
*   **Physics Engine Drop-Zone:** An interactive falling-text block in the footer using `matter.js`. The structured typography drops, bounces, and realistically scatters outward with force upon the user's cursor hovering across them.

## 🛠️ Technologies Used

*   **HTML5 & Vanilla CSS3:** No bloated frameworks; structurally semantic DOM with robust Vanilla CSS architecture utilizing scoped CSS variables (`--ink`, `--canvas`, `--accent`).
*   **GSAP (GreenSock):** Core animation engine for preloader sequencing, reveal triggers, and complex timeline orchestration natively bound to the window.
*   **ScrollTrigger:** A GSAP native plugin driving scroll-linked visuals (element `.reveal` triggers, driving the exact rotation and `z-axis` of the 3D gallery mapping).
*   **Lenis:** Momentum-based smooth scrolling library applied at the document layer for an organic, native application scroll-wheel feel.
*   **Three.js:** Dedicated WebGL canvas rendering for both the animated fluid background gradient and the entire 3D gallery perspective mechanism.
*   **Matter.js:** Lightweight 2D Physics engine implemented for chaotic, fun typography manipulation acting upon cursor proximity rather than clicks.

## 📁 Project Structure Explained

1.  **The Preloader (`#preloader`)**
    The immersive entry viewport. Uses exact vector SVG `<path>` elements mapped through JavaScript mathematical calculations to natively draw, delay, and subsequently use a geometric GSAP scale mapping to dynamically "fly through" the visual hole of the logo.

2.  **The Hero Segment (`#hero`)**
    Displays the fluid background (`#gradient-canvas`) directly beneath the HTML layer. Features standard cascading typography built natively utilizing `display: contents` to marry semantic HTML heading structures alongside exact CSS Grid placement logic. Includes a seamless, infinite CSS SMIL/SVG tracking snake-path text animation wrapping around the interface.

3.  **About Philosophy Room (`.about`)**
    A structured typographic break providing Knel's overarching mission statement, tactical capabilities, and system software stacks correctly mapped via CSS constraints and flexible wrap-logic with subtle `.reveal` GSAP entrance triggers locking into the scroll position.

4.  **Portfolio Interactive Gallery (`#portfolio`)**
    The heavy-lifting WebGL environment. The gallery strictly renders a dedicated `<canvas>`, bypassing the HTML DOM entirely for optimal frame performance logic. The raw window scroll progressively manipulates `targetScroll` to inherently trigger camera repositioning alongside Z-axis geometry shifts. The dynamically matching DOM interface objects (`.slide-info`) overlay atop this WebGL scene globally, tracking their `safeIndex` and crossfading respectively as the `Three.js` camera actively passes focal parameters.

5.  **Dynamic Contact Module (`#contact`)**
    Contains an SVG-blob bounding container wrapped in flexible styling matrices. The typography continuously loops/orbits the SVG bounding box autonomously tracking along SMIL/SVG `<textPath>` components without javascript calculations. This layout isolates text paths so they specifically overflow outside their respective bounding container structure providing a multi-dimensional overlapping feel.

6.  **Interactive Sandbox Footer (`.footer`)**
    Features an isolated physics collision container (`.falling-text-area`). `Matter.js` autonomously drops an exact array of separated words into a mathematical physics gravity well dynamically locking them into bounds, while simultaneously running a geometric raycaster event tracking the user's mouse position to physically blast the simulated text objects outward symmetrically simulating wind or localized gravitational propulsion.

---

## 🎬 Guide: Adding YouTube Links on your Portfolio Cards

Because the entire portfolio 3D gallery environment physically renders in pure **`Three.js` (WebGL)** on a solitary `<canvas>` space, typical HTML features like `<a>` href tags cannot natively wrap around 3D WebGL material planes intuitively. However, we have strategically separated standard HTML text elements completely over the top of the canvas via absolute positioning using `.slide-info` DOM structures. 

To properly link out to external YouTube content associated directly with a showcase presentation plane, simply utilize a standard HTML web anchor button and position it underneath the appropriate `slide-info` block within `index.html`.

### The Simple Process:

**Step 1:** In `index.html`, locate any of your existing project descriptions via `<div class="slide-info" id="slide-[NUMBER]">`.
**Step 2:** Underneath your `.slide-info__meta` container inside that exact group, freely drop in a `<a target="_blank">` linking to the matching video. Example:

```html
<div class="slide-info__meta">
    <span class="slide-info__label">Type</span>
    <span class="slide-info__value">Short-form</span>
    <!-- ...other metadata... -->
</div>

<!-- ================= ADD THIS LINK ================= -->
<a href="https://youtu.be/YOUR_EXACT_VIDEO_ID" target="_blank" class="gallery-watch-btn">
    Watch on YouTube ↗
</a>
<!-- ================================================= -->
```

**Step 3:** To ensure your new button precisely matches the site branding and functions properly atop the canvas overlay logic, merely drop this specific block of CSS at the very bottom of your `<style>` tag located inside the `<head>` of your environment:

```css
.gallery-watch-btn {
    display: inline-block;
    margin-top: 1.5rem;
    padding: 0.8rem 1.6rem;
    background: var(--accent);
    color: var(--canvas);
    border-radius: 100px;
    font-family: var(--font-m);
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-weight: 500;
    pointer-events: auto; /* IMPORTANT: Restores cursor interactivity layered above canvas depth */
    transition: transform 0.3s ease;
}

.gallery-watch-btn:hover {
    transform: scale(1.05); /* Quick interactive pop on hover */
}
```

By ensuring that UI overlay components retain an explicit property parameter of `pointer-events: auto;`, site visitors can intuitively click the dynamic Youtube action button stationed flawlessly alongside their detailed text descriptions whilst the full-scale 3D gallery planes independently operate unhindered chronologically underneath the DOM.

---

## 🎮 Local Development

Since this specific platform architecture operates fundamentally via pure semantic Native standard HTML/CSS/JS without utilizing precompilers, dense Next.js frameworks or extensive package servers, launching the site via your locale system equates to unparalleled simplicity.

1.  Safely open the exact master project folder inside standard VS Code.
2.  Install the canonical **"Live Server"** IDE Extension publicly published by Ritwick Dey within the integrated marketplace.
3.  On the bottom right blue bezel bar of VS Code natively, click the **"Go Live"** UI mechanism.
4.  The cinematic site will automatically launch seamlessly inside your default OS browser natively binding at `http://127.0.0.1:5500`. 