# Component Specification & Code Implementations
## HRL Bento Split-Hero Announcement Card

### 1. Pure CSS Variables & Tokens

```css
:root {
  --announcement-radius-outer: 28px;
  --announcement-radius-inner: 20px;
  --announcement-radius-pill: 9999px;
  --announcement-radius-chip: 8px;
  
  --announcement-bg-surface: #ffffff;
  --announcement-bg-neutral: #f5f5f7;
  --announcement-border: rgba(0, 0, 0, 0.08);
  --announcement-divider: rgba(0, 0, 0, 0.06);
  
  --announcement-text-primary: #1d1d1f;
  --announcement-text-secondary: #515154;
  --announcement-text-muted: #86868b;
  
  /* Brand Accent Tokens */
  --announcement-accent: #5c9100;
  --announcement-accent-light: rgba(118, 185, 0, 0.10);
  --announcement-accent-border: rgba(118, 185, 0, 0.25);
  --announcement-accent-shadow: rgba(92, 145, 0, 0.28);
}
```

---

### 2. React / TSX Component Code

```tsx
import React from 'react';

interface AnnouncementCardProps {
  platformBadge: string;
  platformSubtitle: string;
  serialNumber: string;
  statusText: string;
  productTitle: string;
  productSubtitle: string;
  productDescription: string;
  authorName: string;
  authorTitle: string;
  rightCategory: string;
  rightHeading: string;
  rightDescription: string;
  highlights: string[];
  primaryCtaText: string;
  primaryCtaUrl: string;
  secondaryCtaText: string;
  secondaryCtaUrl: string;
  tertiaryCtaText?: string;
  tertiaryCtaUrl?: string;
  accentColor?: string;
}

export const BentoAnnouncementCard: React.FC<AnnouncementCardProps> = ({
  platformBadge = "NVIDIA ACCELERATED PLATFORM",
  platformSubtitle = "GEFORCE RTX & DGX WORKSTATIONS · ON-DEVICE LOCAL AI RUNTIME",
  serialNumber = "HRL-NV-RTX-2026 • Verified On-Device GPU Architecture",
  statusText = "NVIDIA RTX & DGX INITIATIVE",
  productTitle = "RTX-LocalAI",
  productSubtitle = "HIGH-PERFORMANCE INFERENCE & PAGED MEMORY ENGINE",
  productDescription = "Engineered for client-side RTX PCs and DGX workstations to deliver sub-millisecond LLM streaming.",
  authorName = "PAVAN KUMAR SADASHIV (HRL)",
  authorTitle = "AI Chief Architect & Founder, HRL International Private Limited",
  rightCategory = "HIGH-THROUGHPUT CLIENT-SIDE AI ARCHITECTURE",
  rightHeading = "On-Device LLM Inference & Zero-Fragmentation Paged Memory",
  rightDescription = "RTX-LocalAI unifies 0.17µs Paged KV-Cache block allocation, sub-5µs CUDA Graph replay execution, and FP8 precision.",
  highlights = [
    "Zero-Fragmentation Paged KV-Cache",
    "CUDA Graph Sub-5µs Replay Engine",
    "0.65ms/tok INT4-AWQ + Speculative",
    "ElevenLabs Voice AI Narration Hub"
  ],
  primaryCtaText = "Launch LocalAI GPU Platform",
  primaryCtaUrl = "#",
  secondaryCtaText = "Read Dedicated Overview Page →",
  secondaryCtaUrl = "#",
  tertiaryCtaText = "View GitHub Repository ↗",
  tertiaryCtaUrl = "#",
  accentColor = "#5c9100"
}) => {
  return (
    <div style={{
      background: '#ffffff',
      border: '1px solid rgba(0, 0, 0, 0.08)',
      borderRadius: '28px',
      padding: '40px 36px',
      boxShadow: '0 20px 48px rgba(0, 0, 0, 0.04), 0 2px 10px rgba(0, 0, 0, 0.02)',
      textAlign: 'left',
      fontFamily: '-apple-system, BlinkMacSystemFont, "SF Pro Text", "Segoe UI", Roboto, sans-serif'
    }}>
      {/* Top Header */}
      <div style={{
        display: 'flex',
        flexWrap: 'wrap',
        justifyContent: 'space-between',
        alignItems: 'center',
        gap: '12px',
        borderBottom: '1px solid rgba(0, 0, 0, 0.06)',
        paddingBottom: '18px',
        marginBottom: '28px'
      }}>
        <div style={{ display: 'inline-flex', alignItems: 'center', gap: '8px' }}>
          <span style={{
            background: accentColor,
            color: '#ffffff',
            fontSize: '10px',
            fontWeight: 700,
            textTransform: 'uppercase',
            letterSpacing: '0.08em',
            padding: '4px 10px',
            borderRadius: '9999px'
          }}>{platformBadge}</span>
          <span style={{ fontSize: '12px', fontWeight: 600, color: '#86868b', textTransform: 'uppercase' }}>
            {platformSubtitle}
          </span>
        </div>
        <div style={{ fontSize: '12px', color: '#86868b', fontFamily: 'ui-monospace, monospace' }}>
          {serialNumber}
        </div>
      </div>

      {/* Grid */}
      <div style={{
        display: 'grid',
        gridTemplateColumns: 'repeat(auto-fit, minmax(320px, 1fr))',
        gap: '36px',
        alignItems: 'stretch'
      }}>
        {/* Left Tactile Tile */}
        <div style={{
          background: 'linear-gradient(165deg, #ffffff 0%, #f5f5f7 100%)',
          border: '1px solid rgba(0, 0, 0, 0.08)',
          borderLeft: `5px solid ${accentColor}`,
          borderRadius: '20px',
          padding: '32px 28px',
          display: 'flex',
          flexDirection: 'column',
          justifyContent: 'space-between',
          minHeight: '360px',
          position: 'relative'
        }}>
          <div>
            <div style={{
              display: 'inline-flex',
              alignItems: 'center',
              gap: '6px',
              background: 'rgba(118, 185, 0, 0.10)',
              border: '1px solid rgba(118, 185, 0, 0.25)',
              padding: '4px 10px',
              borderRadius: '9999px',
              marginBottom: '16px'
            }}>
              <span style={{ width: 5, height: 5, borderRadius: '50%', background: accentColor }} />
              <span style={{ fontSize: '10.5px', fontWeight: 700, color: accentColor, textTransform: 'uppercase' }}>
                {statusText}
              </span>
            </div>
            <h3 style={{ fontSize: '28px', fontWeight: 800, color: '#1d1d1f', margin: 0 }}>{productTitle}</h3>
            <div style={{ fontSize: '11.5px', fontWeight: 700, color: accentColor, marginTop: '6px', textTransform: 'uppercase' }}>
              {productSubtitle}
            </div>
            <p style={{ fontSize: '13.5px', color: '#515154', marginTop: '12px', lineHeight: 1.55 }}>
              {productDescription}
            </p>
          </div>

          <div style={{ marginTop: '28px', paddingTop: '18px', borderTop: '1px solid rgba(0, 0, 0, 0.06)' }}>
            <div style={{ fontSize: '12.5px', fontWeight: 700, color: '#1d1d1f' }}>{authorName}</div>
            <div style={{ fontSize: '11px', color: '#86868b', marginTop: '3px' }}>{authorTitle}</div>
          </div>
        </div>

        {/* Right Details */}
        <div style={{ display: 'flex', flexDirection: 'column', justifyContent: 'space-between' }}>
          <div>
            <div style={{ fontSize: '11px', fontWeight: 700, color: accentColor, textTransform: 'uppercase', marginBottom: '6px' }}>
              {rightCategory}
            </div>
            <h3 style={{ fontSize: '22px', fontWeight: 700, color: '#1d1d1f', margin: '0 0 12px 0' }}>
              {rightHeading}
            </h3>
            <p style={{ fontSize: '13.5px', color: '#515154', lineHeight: 1.55, margin: '0 0 18px 0' }}>
              {rightDescription}
            </p>

            <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(180px, 1fr))', gap: '8px', marginBottom: '24px' }}>
              {highlights.map((item, idx) => (
                <div key={idx} style={{
                  background: '#f5f5f7',
                  borderRadius: '8px',
                  padding: '8px 12px',
                  fontSize: '12px',
                  fontWeight: 500,
                  color: '#1d1d1f',
                  display: 'flex',
                  alignItems: 'center',
                  gap: '6px'
                }}>
                  <span style={{ width: 4, height: 4, borderRadius: '50%', background: accentColor }} />
                  <span>{item}</span>
                </div>
              ))}
            </div>
          </div>

          <div style={{ display: 'flex', flexWrap: 'wrap', gap: '12px', alignItems: 'center' }}>
            <a href={primaryCtaUrl} style={{
              background: accentColor,
              color: '#ffffff',
              padding: '11px 22px',
              borderRadius: '9999px',
              fontSize: '13.5px',
              fontWeight: 600,
              textDecoration: 'none',
              boxShadow: `0 4px 14px ${accentColor}44`
            }}>
              {primaryCtaText} ↗
            </a>
            <a href={secondaryCtaUrl} style={{
              background: '#ffffff',
              border: `1px solid ${accentColor}44`,
              color: accentColor,
              padding: '11px 18px',
              borderRadius: '9999px',
              fontSize: '13.5px',
              fontWeight: 600,
              textDecoration: 'none'
            }}>
              {secondaryCtaText}
            </a>
            {tertiaryCtaText && (
              <a href={tertiaryCtaUrl} style={{
                background: '#f5f5f7',
                border: '1px solid rgba(0, 0, 0, 0.08)',
                color: '#1d1d1f',
                padding: '11px 18px',
                borderRadius: '9999px',
                fontSize: '13.5px',
                fontWeight: 600,
                textDecoration: 'none'
              }}>
                {tertiaryCtaText}
              </a>
            )}
          </div>
        </div>

      </div>
    </div>
  );
};
```
