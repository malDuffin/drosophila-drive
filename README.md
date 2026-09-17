# Drosophila Drive

You drive. Every other car on the road is a fruit fly.

A 3D browser game: your car is human-controlled; NPC cars are steered by a **Drosophila-inspired visuomotor circuit** (photoreceptors → lamina ON/OFF → T4/T5 Reichardt detectors → HS optomotor + LPLC2 looming → Giant Fiber escape → descending neurons).

## This is not the 166k-neuron MaleCNS graph

Google/Janelia MaleCNS v1.0 (~166,000 neurons, tens of millions of synapses) cannot run in real time for a pack of cars in a browser. This game uses the *same family of circuits* those neurons implement — looming, optic flow, heading, escape — with a few dozen units per car.

If you want the measured connectome driving from pixels, see [suanmiao/fly-self-driving](https://github.com/suanmiao/fly-self-driving) and [MarkUnthank/flyhard](https://github.com/MarkUnthank/flyhard).

## Play

1. Open `index.html` in Chrome, Firefox, or Edge.
2. If modules are blocked from `file://`, run `python3 -m http.server` in this folder and visit `http://localhost:8000`.
3. Click **ENTER THE ROAD** or press Enter.

### Controls

| Key | Action |
| --- | --- |
| **W / ↑** | Accelerate |
| **S / ↓** | Brake / reverse |
| **A D / ← →** | Steer |
| **C** | Cycle camera (chase / hood / high) |
| **Tab** | Pin the next fly-car brain |
| **H** | How the brain drives |
| **M** | Mute |
| **R** | Reset player |
| **Esc** | Title screen |

### What you should notice

Fly-cars do not hold a racing line. They match optic flow, swerve late when something *looms*, and panic-saccade if you charge them. That twitch is the Giant Fiber.

## Circuit (per NPC)

1. Compound-eye raycasts (ommatidia)
2. Photoreceptor adaptation (high-pass)
3. Lamina ON / OFF
4. T4/T5 Hassenstein–Reichardt elementary motion detectors
5. HS cells — wide-field optomotor yaw
6. LPLC2 / LC4 — looming / expansion
7. Giant Fiber — all-or-none escape
8. PFL3-style heading + gap taxis
9. Descending neurons — steer and throttle

Live HUD: eye raster, EMD bars, looming η, GF spike, motor readout.

## Credits

MIT. Biology motifs from published *Drosophila* work (Hassenstein–Reichardt EMDs, Gabbiani looming η = θ̇/θ, Ache / Morimoto LPLC2 → Giant Fiber). Weights in this game are designed, not trained on MaleCNS.
