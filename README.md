Synthwave Fireplace 🔥🌌
A cozy, synthwave‑themed HTML fireplace with particle‑based neon flames and generative fire audio (white noise + random pops & crackles). Designed to feel like a fireplace in a living room, but from a retro‑futuristic alternate universe.

✨ Features
Neon flame particles
Particle system with long trails using a fading canvas buffer
Synthwave palette (purple → magenta → cyan)
Organic motion and decay for a natural but stylized flame
Generative fire audio
Continuous filtered white noise for the fire “roar”
Randomized pops and crackles using Web Audio oscillators
Toggle sound on/off with a single button
Living‑room style fireplace
Mantel, pillars, firebox, and hearth styled as a real fireplace
Clean neon “log” shapes (no odd patterns)
Synthwave grid on the back wall of the firebox
Responsive layout
Scales to desktop and mobile
Zoomed‑in focus on the firebox so it feels like a dedicated fireplace screen
🚀 Getting Started
1. Clone or download
bash
Copy
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
(Or just copy the index.html into any folder.)

2. Open in a browser
You can simply open the index.html file directly:

Visit the live app: 
```text
https://marusame00.github.io/synthwave-fireplace/
```

Double‑click index.html, or
Right‑click → “Open With” → your browser
For best results and to avoid any local file / audio restrictions, you can also serve it with a simple dev server, e.g.:

bash
Copy
# Using Python 3
python -m http.server 8000

# Then visit:
# http://localhost:8000/index.html
📁 File Structure
text
Copy
.
├── index.html    # All HTML, CSS, and JS for the synthwave fireplace
└── README.md     # This file
Everything is self‑contained in index.html (no external assets needed).

💻 Implementation Details
Particles
Each flame particle:
Has position, size, velocity, lifetime, and decay
Uses a radial gradient for a glowing, neon flame effect
Is rendered on a canvas with a semi‑transparent background fill (rgba(5,0,15,0.15)) each frame to create smooth trails
New particles are spawned near the base of the firebox:
X: middle 50% of the canvas
Y: slightly above the logs
Audio
Uses the Web Audio API
White noise:
ScriptProcessorNode (or equivalent) generates random samples
Passed through a low‑pass filter (~800 Hz) so it sounds like fire, not harsh hiss
Crackles:
Random intervals trigger:
A short‑lived oscillator
With an exponential gain envelope to create a “pop”
Audio is started lazily on first user interaction (click) to comply with browser autoplay policies.
🔊 Controls
Sound Button (top‑right corner):
Sound: ON → audio running (white noise + crackles)
Sound: OFF → audio context suspended
📱 Mobile & Responsiveness
Uses flexible widths (vw, vh, percentages) for:
Mantel, firebox, hearth, and pillars
Firebox height adapts slightly in portrait vs landscape to keep the flame nicely framed.
No external dependencies; just HTML + CSS + JS.
🛠 Customization
You can tweak a few things easily in index.html:

Flame behavior
Particle count: numParticles in createParticles()
Speed & direction: speedX, speedY in the Particle constructor
Color range: this.hue = Math.random() * 60 + 280;
Audio character
White noise volume: gainNode.gain.value
Filter tone: filter.frequency.value
Crackle frequency & intensity:
Interval in setInterval inside startCrackles()
Oscillator frequency.value and envelope in playCrackle()
Overall look
Background gradients in body and #firebox
Borders and glow colors for a more subtle or more intense synthwave look
⚠️ Browser Support
Modern browsers (Chrome, Edge, Firefox, Safari) should work.
The audio relies on the Web Audio API:
Some older/locked‑down browsers may require a user interaction before audio starts.
If you see no sound, click once in the page and then toggle the sound button.
📝 License
Use, modify, and adapt freely for your own fireplace screensavers, ambient setups, or just to vibe while coding. Add a mention or link back if you share it, which helps others find it.
