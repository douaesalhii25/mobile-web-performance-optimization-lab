# Mobile Web Performance Optimization Lab

## Experiment : Loading, Rendering & Code Optimization

**Author:** Douae Salhi  
**Program:** Bachelor of Computer Science, 3rd Year  
**University:** Southwest Petroleum University (SWPU), China

---

## Overview

This experiment demonstrates three core mobile web performance optimization techniques:

1. **DOM manipulation optimization** – Reducing reflows using DocumentFragment
2. **Animation optimization** – Replacing layout thrashing with GPU-accelerated transforms
3. **Resource loading optimization** – Implementing async font loading to eliminate render-blocking

---

## Before vs After

| Aspect | Before (Unoptimized) | After (Optimized) |
|--------|---------------------|-------------------|
| Product loading | 200 reflows | 1 reflow |
| Animation | Choppy (~30fps) | Smooth (60fps) |
| Font loading | Render-blocking | Async + preconnect |

---

## Files

| File | Description |
|------|-------------|
| `before.html` | Unoptimized version (baseline) |
| `after.html` | Optimized version with all improvements |

---

## Optimizations Applied

### 1. DOM Batching with DocumentFragment

**Before:**
```javascript
for (let i = 0; i < 200; i++) {
    container.appendChild(card); // Reflow on each iteration
}

**After:**
const fragment = document.createDocumentFragment();
for (let i = 0; i < 200; i++) {
    fragment.appendChild(card); // No reflow
}
container.appendChild(fragment); // Single reflow

2. GPU-Accelerated Animation

Before: Used offsetLeft + left (forces layout recalculation)

After: Used transform: translateX() (GPU accelerated, no layout thrashing)

3. Font Loading Optimization

Before: Standard <link> tag blocked rendering

After: Preconnect + media="print" trick for non-blocking font loading

---

Results

· Product load time: ~800ms → ~200ms (4x faster)
· Animation frame rate: ~30fps → 60fps (smooth)
· Layout recalculations: 200+ → 1

---

Tools Used

· VS Code
· Chrome Browser
· Chrome DevTools
· Git & GitHub

---

How to Run

1. Clone this repository
2. Open before.html in a browser
3. Click "Load Products" and "Animate Box"
4. Repeat with after.html
5. Observe the performance difference

---

Conclusion

The optimized version achieves significant performance improvements while maintaining identical visual output, proving that performance optimization enhances user experience without sacrificing design.

---

Course Information

· Course: Mobile applications and Performance Optimization
· Experiment Date: April 2026

---

Connect with Me

GitHub: douaesalhii25

---

This is part of my 3rd year computer science bachelor's lab work at SWPU, China.

```

---