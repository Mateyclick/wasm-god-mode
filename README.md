# Ruby DOM Takeover 💎🕸️

> **Live Demo:** [Click here to launch the system](https://mateyclick.github.io/wasm-god-mode/) 

### ⚠️ This is not a standard JavaScript website.
This project is a technical experiment running **CRuby 3.2 natively in your browser** via WebAssembly (WASM/WASI).

The JavaScript layer has been stripped down to a minimal "dumb" rendering engine. The entire application logic—routing, DOM manipulation, 3D physics, and state management—is handled by a **Ruby Kernel** embedded directly in the HTML.

---

## 🏗️ Architecture: "The Puppeteer Pattern"

Traditional web apps use JavaScript for logic and state. In this architecture, **Ruby is the Operating System**:

* **HTML:** "Dead" on load. No inline `onclick` events. Logic-less.
* **JavaScript:** Acts only as a bridge/driver for WebGL (Three.js) and raw DOM access.
* **Ruby:** The "Brain". It injects event listeners, generates UI components, calculates physics frames (60 FPS), and manages the virtual file system.

### File Structure
* `index.html`: **The Monolith.** Contains the UI, the 3D Engine, and the complete Ruby Source Code embedded in `<script type="text/ruby">` tags.

---

## 🚀 Key Features

### 1. Zero-JS Routing & DOM Control
Navigation buttons are generated and controlled by Ruby.
```ruby
# Real code from the embedded script
ROUTES.each do |r|
  DOM.on_click("nav-btn-#{r}") { navigate(r) }
end
```

### 2. High-Performance Physics Loop
The background neural network simulation (Boids/Particles) is calculated in Ruby.
* **Vector Math:** Performed in Ruby.
* **Garbage Collection:** Optimized to prevent stuttering during the render loop.
* **Bridge:** Ruby sends raw coordinates to Three.js for rendering.

### 3. "God Mode" (In-Browser REPL)
The site includes a live terminal that allows direct interaction with the Ruby runtime instance.

**How to use it:**
1. Click `>_ TERMINAL` in the footer.
2. Type commands to alter the physics engine in real-time.

| Command | Effect |
| :--- | :--- |
| `chaos` | Increases entropy and removes friction. |
| `calm` | Restores the system to the default Zen state. |
| `speed = 5.0` | Overclocks the time multiplier. |
| `color "#ff0000"` | Changes the neural network color (Hex/String). |
| `self` | Inspects the current GodMode Ruby object. |
