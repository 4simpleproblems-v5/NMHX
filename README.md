# Noise Map Hash Extension (NMHX)

Noise Map Hash Extension (NMHX) is an experimental extension of the SHA‑512 cryptographic function. It generates a 2D or 3D noise map based on the user's current local time, converting that time into a SHA‑512 hash and then processing the noise map. NMHX2 uses a 2D map for older hardware, and NMHX3 uses a 3D map for newer systems.

> **Note:** This implementation is primarily for testing, visualization, and token generation. It is **not a replacement** for secure cryptographic functions.

---

## Features

* **Time-Based Entropy**: Incorporates the user's local device time down to milliseconds for variability.
* **Noise Map Expansion**: Converts hash input into a chaotic noise field to amplify small differences.
* **Dimensional Flexibility**:

  * NMHX2 → 2D noise map for older hardware.
  * NMHX3 → 3D noise map for modern hardware.
* **Chaotic Sampling**: Samples the noise map along a pseudo-random crawl path to generate final codes.
* **SHA‑512 Anchoring**: Uses SHA‑512 at both the base and final compression stages for strong cryptographic grounding.
* **Visual Representation**: Optional visualization of noise maps to inspect patterns and behaviors.

---

## Usage

1. **Generate Base Hash**: Take the current timestamp and optional salt, and hash it with SHA‑512.
2. **Create Noise Map**: Use the hash to seed a 2D or 3D noise map.
3. **Crawl the Map**: Sample values along a deterministic but chaotic path.
4. **Final Hash**: Compress the sampled values using SHA‑512 to produce the NMHX code.
5. **Visual Output (Optional)**: Render the noise map for inspection or debugging.

---

## Categories

### Entropy Sources

* Local device time
* Optional user salt or seed
* Monotonic counters or timers

### Core Components

* SHA‑512 hash function
* 2D/3D noise map generation
* Chaotic sampling / crawl logic
* Final compression hash

### Output

* Fixed-size NMHX code (512 bits)
* Optional visual noise map (grayscale)

### Use Cases

* One-time tokens
* Session identifiers
* Nonces for experiments
* Educational visualization of hash expansion

### Limitations

* **Not suitable** for password storage or critical encryption keys.
* Noise map patterns may leak if misused.
* Security depends entirely on SHA‑512; the noise map is additional obfuscation.

---

## Future Enhancements

* Interactive visualization of NMHX crawls
* Adjustable walk lengths and noise resolutions
* Optional NMHX3 z-axis animation for 3D exploration
* Benchmarking against SHA‑512 and SHA‑3 outputs
