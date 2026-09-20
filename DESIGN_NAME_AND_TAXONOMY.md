# Official Design Taxonomy & Nomenclature Guide
## HRL Company Page Announcement Design

### 1. Primary Design Nomenclature

When planning, designing, or coding UI updates, this component is classified under:

#### A. **Bento Split-Hero Announcement Card** (Primary Industry Standard)
- **Why**: "Bento Grid" refers to modular Japanese lunchbox-style asymmetric UI boxes popularized by Apple Keynotes, Microsoft Fluent, and Linear. "Split-Hero" describes the distinct two-compartment layout where the left side acts as the tactile visual anchor and the right side presents actionable specifications.

#### B. **Apple-Style Showcase Modal / Banner**
- **Why**: Utilizes Apple's trademark design principles:
  - 28px outer corner rounding (`border-radius: 28px`)
  - Sub-pixel hairline gray borders (`rgba(0, 0, 0, 0.08)`)
  - Ambient elevation shadows with zero harsh edges
  - Full-pill pill-shaped interactive elements (`border-radius: 9999px`)
  - Clean San Francisco / Inter typography hierarchy.

#### C. **Linear Precision Tech Callout**
- **Why**: Popularized by Linear.app and Vercel for high-performance developer tools:
  - High-contrast vertical accent edge (`border-left: 5px solid [ACCENT]`)
  - Status indicator dot pills (`5px` rounded colored dot)
  - Monospace revision tags (`ui-monospace, monospace` for serial strings)
  - Soft-surface feature chips (`#f5f5f7` pill container with leading dot).

---

### 2. Multi-Theme Color Palettes for Upcoming Updates

This design system supports four executive colorways for future releases:

| Theme | Accent Color | Glow Shadow | Use Case |
| :--- | :--- | :--- | :--- |
| **NVIDIA Emerald (Current)** | `#5c9100` | `rgba(92, 145, 0, 0.28)` | AI Systems, GPU Compute, RTX Runtimes |
| **Sovereign Sapphire** | `#0071e3` | `rgba(0, 113, 227, 0.28)` | Corporate Announcements, Sovereign Grants, US Expansion |
| **Titanium Dark** | `#0a0a0c` | `rgba(255, 255, 255, 0.15)` | Dark-mode engines, Core Systems, C++ Kernels |
| **Quantum Amethyst** | `#7928ca` | `rgba(121, 40, 202, 0.28)` | Creative Tools, Video Plugins, ElevenLabs Voice AI |

---

### 3. Usage Guidelines for HRL Websites
1. **Placement**: Directly below the hero section or atop major product sections to highlight verified milestones.
2. **Typography**: Always pair heavy title weights (`font-weight: 800`) with medium body text (`font-weight: 400` to `500`).
3. **CTAs**: Limit to a maximum of 3 actions (Primary Action, Detailed Deep Dive, Code/GitHub Reference).
