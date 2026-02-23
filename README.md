# ⚛️ Quantum Kinetic: Atomic Orbital Visualizer

A real-time, gesture-controlled simulation of electron probability distributions. This project visualizes the $s, p, d,$ and $f$ orbitals using a particle-based engine, allowing users to interact with quantum states through hand movements.


## 💡 The Project Concept
I built this because atomic orbitals are often taught as static 2D images. I wanted to create a "Quantum Playground" where you could physically move, scale, and switch between orbital states using AI-powered hand tracking.

### 1. The Physics (Quantum Wave Functions)
* **Orbital Logic:** The simulation calculates the probability density ($|\psi|^2$) for different quantum states. 
* **Dynamic Rendering:** It uses a rejection sampling algorithm to distribute 15,000 particles in 3D space based on the mathematical shape of $s$ (spherical), $p$ (dumbbell), $d$, and $f$ orbitals.
* **Kinetic Jitter:** To represent the "uncertainty" and energy of electrons, I implemented a custom jitter logic that keeps the particles in a state of constant quantum motion.

### 2. The Interaction (AI Gesture Engine)
Using **Google MediaPipe**, I mapped specific hand gestures to quantum variables:
* **Positioning:** Your palm position moves the entire orbital field in 3D space.
* **Quantum Scale:** A "Pinch" gesture (Thumb to Index) triggers a logarithmic scaling of the field.
* **State Cycling:** Showing a "Victory Sign" (Index and Middle finger up) triggers a mode-switch, cycling through the $s \rightarrow p \rightarrow d \rightarrow f$ orbitals.

---

## 🛠️ Tech Stack
* **Language:** JavaScript (ES6+), Three.js (WebGL)
* **AI/ML:** MediaPipe Hands
* **Fonts:** Orbitron (Google Fonts) for that "Control Terminal" aesthetic.

## 🔧 Engineering Challenges
* **State Transitions:** Implementing a debounce timer for the "Victory Sign" gesture so the orbitals don't cycle too fast when a hand is detected.
* **Smoothing:** Used **Linear Interpolation (LERP)** to ensure that when the AI detects a hand move, the particles follow with a smooth, "weighty" kinetic feel.
