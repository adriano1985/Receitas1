# Design Guidelines: PWA Recipe Manager

## Design Approach

**Selected Approach:** Design System - Material Design 3  
**Justification:** Recipe apps require high information density, clear hierarchy for text-heavy content, and standard interaction patterns. Material Design 3 provides excellent typography scales, card systems, and form components ideal for content management applications.

**Reference Inspiration:** Drawing patterns from Paprika Recipe Manager and Mela for recipe-specific UX patterns while maintaining Material Design's structural foundation.

**Core Principles:**
- Content-first hierarchy prioritizing recipe readability
- Efficient input workflows for quick recipe entry
- Scannable recipe cards with visual differentiation
- Mobile-optimized for kitchen use scenarios

---

## Typography

**Font Family:** Inter (primary), Merriweather (recipe content)

**Hierarchy:**
- App Title/Headers: Inter Bold, 24px (mobile), 32px (desktop)
- Recipe Titles: Inter Semibold, 20px (cards), 28px (detail view)
- Section Labels: Inter Medium, 14px, uppercase tracking
- Recipe Content: Merriweather Regular, 16px (ingredients/instructions)
- Body Text: Inter Regular, 15px
- Metadata/Tags: Inter Regular, 13px
- Button Text: Inter Medium, 15px

---

## Layout System

**Spacing Primitives:** Tailwind units of 2, 4, 6, and 8  
Common patterns: p-4, gap-6, m-8, space-y-4

**Container Structure:**
- Mobile: Full-width with px-4 padding
- Desktop: max-w-6xl centered container with px-8

**Grid Systems:**
- Recipe Cards: 1 column (mobile), 2 columns (tablet), 3 columns (desktop)
- Form Layout: Single column, max-w-2xl for optimal form completion

---

## Component Library

### Navigation
**Bottom Tab Bar (Mobile Primary):**
- Fixed bottom navigation with 3 tabs: Browse, Add Recipe, Categories
- Active state with icon fill and subtle indicator line
- Height: 64px with icons at 24px

**Top App Bar (Desktop/Secondary):**
- Contains app title, search input, and filter dropdown
- Height: 64px, sticky positioning

### Recipe Cards
**Structure:**
- Elevated card with rounded-lg corners
- Recipe thumbnail placeholder (16:9 aspect ratio, h-40)
- Title (2-line truncation), category badge, time/servings metadata
- Tap target: entire card
- Spacing: p-4 internal, gap-6 between cards

### Forms (Add/Edit Recipe)

**Layout:**
- Full-height scrollable form with sections
- Section dividers with subtle borders
- Generous spacing between fields (space-y-6)

**Input Fields:**
- Recipe Name: Single line text input, large (text-lg)
- Ingredients: Textarea with min 6 rows, placeholder showing multi-line format
- Instructions: Textarea with min 8 rows
- Category: Multi-select chip input or dropdown
- Metadata: Inline inputs for prep time, cook time, servings

**Actions:**
- Sticky bottom action bar (mobile) or floating action area (desktop)
- Primary "Save Recipe" button (full-width mobile, auto desktop)
- Secondary "Cancel" text button

### Recipe Detail View

**Header:**
- Recipe title (large, bold)
- Category badges, metadata (time, servings) in horizontal layout
- Action buttons: Edit, Delete (icon buttons, top-right)

**Content Sections:**
- Clear section headers: "Ingredients", "Instructions"
- Ingredients: Bulleted list with checkboxes for interactive use
- Instructions: Numbered steps with generous line-height (1.7)
- Spacing between sections: mt-8

### Category System
**Category Chips:**
- Rounded-full pills with px-4 py-2
- Dismissible (x icon) when editing
- Color-neutral with border treatment
- Horizontal scrollable row when multiple

**Category Filter:**
- Horizontal chip selection at top of browse view
- "All" + category options
- Active state with solid background

### Empty States
- Centered content with icon (96px), heading, description
- "Add Your First Recipe" CTA button
- Appears when no recipes or filtered results

### Search & Filter
**Search Input:**
- Prominent placement in top bar or browse header
- Search icon prefix, clear button suffix
- Instant filtering of recipe list

---

## Animations

**Minimal Motion Philosophy:**
- Card hover: Subtle elevation increase (shadow transition)
- Form focus: Smooth border color transition
- Tab switching: Crossfade content change
- List filtering: Fade-out/fade-in effect (200ms)
- NO scroll-triggered animations
- NO complex page transitions

---

## Images

**Hero Section:** None - this is a utility app prioritizing immediate access to content

**Recipe Cards:**
- Placeholder image area (16:9 ratio) in soft neutral background
- Future support for recipe photos
- Fallback: Category-based icon or color block

**Empty States:**
- Simple line-art icon (cooking utensils, recipe book)

---

## Accessibility

- Minimum touch targets: 44x44px
- Form labels always visible (no floating labels)
- Error states with text descriptions, not just color
- Keyboard navigation for all interactive elements
- Semantic HTML throughout (proper heading hierarchy)
- Focus indicators on all interactive elements with 2px outline

---

## PWA-Specific Considerations

**Install Prompt:**
- Subtle banner at bottom on first visit
- "Install app for offline access" message
- Dismissible with "Not now" option

**Offline Indicator:**
- Toast notification when offline
- Disabled state for features requiring connectivity (future: sync)

**App Shell:**
- Immediate navigation chrome load
- Content skeleton during data fetch from LocalStorage