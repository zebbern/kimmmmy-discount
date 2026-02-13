---
name: new-component
description: Scaffold a new React component with types, tests, and styles following project conventions
---

# New Component Scaffold

Create a new React component following project conventions.

## Requirements

Ask the user (or infer from context):

1. **Component name** — PascalCase (e.g., `UserProfile`)
2. **Location** — which directory under `src/components/` or `app/`
3. **Type** — Server Component (default) or Client Component (`'use client'`)

## Files to Create

For a component named `{Name}`:

### 1. Component File: `{Name}.tsx`

```tsx
// If client component, add: 'use client'
import type { {Name}Props } from './types'

export function {Name}({ ...props }: {Name}Props) {
  return (
    <div>
      {/* Implementation */}
    </div>
  )
}
```

### 2. Types File: `types.ts`

```tsx
export interface {Name}Props {
  // Define props
}
```

### 3. Test File: `{Name}.test.tsx`

```tsx
import { describe, it, expect } from 'vitest'
import { render, screen } from '@testing-library/react'
import { {Name} } from './{Name}'

describe('{Name}', () => {
  it('renders successfully', () => {
    render(<{Name} />)
    // Add assertions
  })
})
```

### 4. Index File: `index.ts`

```tsx
export { {Name} } from './{Name}'
export type { {Name}Props } from './types'
```

## Rules

- Follow existing naming conventions in the project
- Use the dark-first color palette from styling instructions
- Server Components by default — only add `'use client'` when needed
- Every component must have at least one test
- Export from barrel file (index.ts)
