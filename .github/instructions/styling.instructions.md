---
name: styling-guidelines
description: Dark-first design patterns, color palette, and CSS/component styling rules
applyTo: "**/*.{tsx,jsx,css,scss,sass}"
---

<core_rules>

- [CRITICAL] This project uses dark-first design — `dark:` Tailwind prefix often FAILS
- [CRITICAL] Portal components (Radix dialogs) do NOT inherit the `dark` class
- [MANDATORY] Always verify dark theme visually after ANY styling changes
  </core_rules>

---

# Dark Mode Implementation

## Why `dark:` Fails

- Portal/overlay components render outside the DOM hierarchy
- CSS specificity issues with component libraries (Radix, Headless UI)
- Global styles can override Tailwind utility classes

## Mandatory Pattern

**NEVER use conditional dark classes:**

```tsx
// ❌ WRONG — causes white/light backgrounds
className = "bg-white dark:bg-gray-900"
className = "bg-gray-50 dark:bg-[#141414]"
```

**ALWAYS use direct dark values:**

```tsx
// ✅ CORRECT — inline style for guaranteed dark
style={{ backgroundColor: '#1a1a1a' }}

// ✅ CORRECT — direct hex in Tailwind (no dark: prefix)
className="bg-[#1a1a1a]"
```

---

# Color Palette

| Element             | Hex Code  |
| ------------------- | --------- |
| Deep background     | `#0a0a0a` |
| Sidebar / secondary | `#141414` |
| Main content        | `#1a1a1a` |
| Elevated / cards    | `#2a2a2a` |
| Hover states        | `#333333` |
| Borders             | `#333333` |
| Text primary        | `#ffffff` |
| Text secondary      | `#9ca3af` |

---

# Component Patterns

## Modal / Dialog

```tsx
<RadixDialog.Content className="dark" style={{ backgroundColor: "#1a1a1a" }}>
  <div style={{ backgroundColor: "#141414" }}>{/* Sidebar content */}</div>
</RadixDialog.Content>
```

## Cards / Elevated Surfaces

```tsx
<div className="rounded-lg border border-[#333333]" style={{ backgroundColor: "#2a2a2a" }}>
  {/* Card content */}
</div>
```

---

<reminders>
- [CRITICAL] Never rely on `dark:` prefix for portal/overlay components
- [MANDATORY] Verify dark theme visually after every styling change
- [CRITICAL] Use direct hex values — inline styles or Tailwind `bg-[#hex]`
</reminders>
