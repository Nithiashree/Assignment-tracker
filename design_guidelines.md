# Design Guidelines: Assignment Tracker App

## Design Approach
**Selected Approach:** Design System (Material Design-inspired with Notion-like simplicity)
**Justification:** Assignment trackers are utility-focused productivity tools where clarity, efficiency, and learnability are paramount. Users need to quickly scan, add, and manage assignments without visual distractions.

**Core Principles:**
- Clean, spacious layouts that reduce cognitive load
- Clear visual hierarchy for assignment status and priority
- Efficient data scanning with strong typography
- Minimal decorative elements; maximum functional clarity

---

## Typography System

**Font Family:** 
- Primary: Inter (Google Fonts) - for UI and body text
- Monospace: JetBrains Mono - for dates/times if needed

**Hierarchy:**
- Page Titles: text-3xl font-semibold (30px)
- Section Headers: text-xl font-semibold (20px)
- Assignment Titles: text-base font-medium (16px)
- Body/Descriptions: text-sm font-normal (14px)
- Metadata (dates, status): text-xs font-medium (12px)

---

## Layout System

**Spacing Primitives:** Use Tailwind units of **2, 4, 6, and 8** consistently
- Component padding: p-4, p-6
- Section spacing: mb-6, mb-8
- Element gaps: gap-4, gap-6

**Container Structure:**
- Max width: max-w-6xl mx-auto
- Page padding: px-4 md:px-6
- Responsive breakpoints: Use md: and lg: for tablet/desktop

---

## Component Library

### Navigation Header
- Fixed top bar with app name/logo (left)
- "Add Assignment" primary action button (right)
- Height: h-16
- Padding: px-6

### Assignment List Container
- Card-based layout with consistent spacing
- Each assignment: rounded-lg border with p-6
- Hover state: subtle elevation change
- Stack vertically with gap-4

### Assignment Card Structure
```
[Assignment Card]
├── Title (prominent, font-medium)
├── Description (text-sm, muted)
├── Due Date (text-xs, with calendar icon)
├── Status Badge (inline, pill-shaped)
└── Action Buttons (subtle, right-aligned)
```

### Add Assignment Form
- Modal overlay approach OR dedicated page
- Form fields stacked vertically with gap-4
- Input labels: text-sm font-medium mb-1
- Input fields: h-10 px-3, rounded-md border
- Textarea for description: h-24
- Submit button: primary style, full-width on mobile

### Status Badges
- Pill shape: rounded-full px-3 py-1
- Size: text-xs font-medium
- Variants: Pending, In Progress, Completed, Overdue
- Use border + subtle background (no strong colors yet)

### Empty State
- Centered vertically in viewport
- Icon (document/assignment icon from Heroicons)
- Message: "No assignments yet"
- CTA: "Create your first assignment" button

---

## Icons
**Library:** Heroicons (outline style for most, solid for emphasis)
- Calendar icon for due dates
- Plus icon for add button
- Check icon for completion
- Document icon for empty states

---

## Layout Patterns

**Main Layout:**
```
[Fixed Header - 64px height]
[Main Content Container - max-w-6xl]
  ├── Page Title + Add Button Row
  ├── Filter/Sort Controls (if added later)
  └── Assignment List Grid
```

**Assignment List:**
- Desktop: Single column, max-w-3xl for optimal reading
- Mobile: Full width with px-4
- Cards have consistent height or grow based on content

**Responsive Behavior:**
- Mobile: Stack all elements, full-width buttons
- Tablet/Desktop: Wider cards with inline action buttons

---

## Interaction Patterns

**Adding Assignment:**
1. Click "Add Assignment" button
2. Modal slides in from right OR navigate to /new page
3. Form with clear field labels and validation
4. Submit shows success message, returns to list with new item highlighted

**Assignment Actions:**
- Hover reveals edit/delete buttons
- Click anywhere on card to view details (optional)
- Status badge clickable to quick-change status

---

## Form Design

**Input Fields:**
- Height: h-10 for single-line, h-24 for textarea
- Padding: px-3 py-2
- Border: border rounded-md
- Focus state: ring-2 outline-none

**Field Layout:**
- Label above input (mb-1)
- Spacing between fields: space-y-4
- Required indicator: asterisk in label

**Button Hierarchy:**
- Primary: "Save Assignment" - prominent
- Secondary: "Cancel" - subtle, ghost style
- Spacing: gap-3, right-aligned

---

## Images

**No hero images** - This is a productivity tool focused on function over marketing appeal. The interface should be immediately useful without scrolling.

---

## Accessibility
- All interactive elements have min-h-10 (40px touch target)
- Form inputs have associated labels
- Focus states clearly visible with ring utility
- Sufficient contrast for all text elements

This design prioritizes speed, clarity, and ease of use - perfect for students managing their assignments efficiently.