# Uniform Distribution of Robots in Single-Dimensional Line and Two-Dimensional Plane

This repository contains the full implementation, simulations, and LaTeX report for our final year project that tackles **uniform robot distribution** across two constrained environments:  
1. A **single-dimensional line**, and  
2. A **two-dimensional circular plane**.

Our objective was to design and compare redistribution algorithms that achieve **balanced configurations** with minimal movement, no collisions, and guaranteed convergence.

---

## 🔍 Project Modules

### 1️⃣ Brute-Force 1D Line Distribution
A median-based approach where:
- The **midpoint** of the robot line is compared with the **median**.
- Robots from the denser side move incrementally (e.g., 0.5 units) toward the midpoint.
- Recursive logic handles **collision avoidance**.
- Movement continues until symmetric distribution is achieved.

💡 **Visual Output:**  
Step-by-step simulation using `matplotlib`, highlighting midpoint, median, and each robot's position.

---

### 2️⃣ Optimized 1D Line Distribution
A faster redistribution algorithm that:
- Counts the number of robots on each side of the midpoint.
- Shifts only the **minimum required number of robots** from the denser side to the sparse side.
- Respects spacing by treating robots as **unit-diameter circles**.
- Ensures **collision-free** convergence with fewer steps than the brute-force version.

💡 **Visual Output:**  
Initial and final robot layouts with labeled positions and transitions, emphasizing efficient movement.

---

### 3️⃣ Uniform Distribution in a 2D Circular Plane
Extends redistribution into a 2D bounded region:
- The circle is sliced into **horizontal lines (y-levels)**.
- Each line is treated independently as a 1D distribution problem.
- Robot positions are **mirrored** about the vertical axis (`x = 0`) to enforce symmetry.
- The approach supports both even and odd distributions.

💡 **Visual Output:**  
Animated and frame-by-frame visualizations of robots symmetrically aligning within a circle.

---

## 🖥️ Simulations

All simulations are implemented in **Python**, and visualizations are created using:

- `matplotlib`: For plotting and animation
- `tqdm`: Progress bars (for 1D brute-force)
- `ImageMagick` (optional): To stitch animation frames into GIFs or MP4s
- `collections`, `time`, `sys`, `typing`: For internal logic and type annotations

Simulations include:
- **Live animation**
- **Frame snapshots** for LaTeX reports
- **Labeled robot IDs and coordinates**
