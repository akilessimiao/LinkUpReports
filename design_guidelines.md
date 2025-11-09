# LinkUp Construction Measurement System - Design Guidelines

## Design Approach
**System Selected**: Modern Dashboard Design (inspired by Linear, Notion, and enterprise SaaS applications)

**Rationale**: Data-heavy construction management system requiring clear information hierarchy, efficient data entry, and professional report generation. Focus on usability, scannable tables, and print optimization.

## Core Design Principles
1. **Clarity First**: Information density without clutter - every element serves data presentation or action
2. **Professional Authority**: Construction industry expectations - trustworthy, robust, enterprise-grade
3. **Efficient Workflows**: Minimize clicks for common tasks (data entry, report generation, printing)

## Typography System

**Font Family**: Inter (via Google Fonts CDN)
- Primary: Inter for all UI elements
- Monospace: 'Roboto Mono' for numeric data and currency values

**Type Scale**:
- Headings: text-2xl (dashboard titles), text-xl (page headers), text-lg (section headers)
- Body: text-base (default), text-sm (table cells, secondary info)
- Small: text-xs (labels, metadata)
- Weights: font-normal (400), font-medium (500), font-semibold (600), font-bold (700)

**Data Presentation**:
- Currency values: font-mono, font-semibold, text-right alignment
- Table headers: font-semibold, text-sm, uppercase tracking-wide
- Worker names: font-medium
- Companies: text-sm, font-normal

## Layout System

**Spacing Primitives**: Use Tailwind units of 2, 4, 6, and 8 (p-2, m-4, gap-6, space-y-8)
- Compact spacing (2-4): Within components, table cells
- Standard spacing (4-6): Between related elements
- Section spacing (6-8): Between distinct content areas

**Grid Structure**:
- Sidebar navigation: Fixed width 256px (w-64)
- Main content: flex-1 with max-w-7xl container
- Forms: max-w-2xl for focused data entry
- Tables: w-full with horizontal scroll on mobile

**Container Strategy**:
- Application shell: Full viewport height (h-screen) with flex column
- Content area: Scrollable overflow-y-auto
- Modals/dialogs: max-w-4xl for large forms, max-w-2xl for confirmations

## Component Library

### Navigation
**Sidebar** (Admin & User views):
- Logo placement at top (h-12)
- Navigation items with icons (Heroicons)
- User profile at bottom
- Active state indicators
- Collapsible on mobile (hamburger menu)

**Top Bar**:
- Breadcrumb navigation
- Quick actions (Nova Medição, Imprimir)
- User avatar dropdown

### Data Tables
**Measurement Tables**:
- Sticky header row
- Alternating row backgrounds for scannability
- Right-aligned numeric columns
- Hover states for row selection
- Compact padding (px-4 py-2)
- Responsive: Stack to cards on mobile (<768px)

**Daily Attendance Grid**:
- Fixed first columns (Nome, Empresa, APT)
- Horizontal scroll for date columns
- Checkbox/indicator cells (w-8 h-8)
- Visual totals row with distinct styling

### Forms
**Data Entry**:
- Label above input layout
- Input fields: h-10, px-3, rounded-md
- Select dropdowns: Consistent height
- Date pickers: Native or minimal calendar
- Currency inputs: Formatted with R$ prefix, right-aligned
- Validation: Inline error messages below fields

**Form Actions**:
- Primary CTA: Right-aligned, h-10 px-6
- Secondary actions: Ghost/outline style
- Cancel: Always available, left-aligned

### Cards & Panels
**Dashboard Cards**:
- Rounded corners (rounded-lg)
- Subtle elevation (shadow-sm)
- Header with icon and title (text-lg font-semibold)
- Metric display: Large numbers (text-3xl font-bold) with labels
- Padding: p-6

**Report Panels**:
- Clean borders, no shadows (print-friendly)
- Dense information layout
- Company/obra info header
- Signature/approval areas

### Buttons
- Height: h-10 for primary actions, h-8 for secondary
- Padding: px-4 (small), px-6 (default)
- Border radius: rounded-md
- States: Default, hover, active, disabled
- Icon buttons: w-10 h-10, centered icon

### Icons
**Library**: Heroicons (via CDN) - outline style for navigation, solid for actions
- Navigation: 24px (w-6 h-6)
- Inline actions: 20px (w-5 h-5)
- Small indicators: 16px (w-4 h-4)

## Screen Layouts

### Login Page
- Centered card (max-w-md)
- Logo at top (h-16)
- Title "Sistema de Medições LinkUp"
- Email/password fields
- "Lembrar-me" checkbox
- Primary login button (w-full)

### Dashboard (Post-Login)
- Sidebar + Main content layout
- Top metrics cards (grid-cols-3): Total Medições, Diárias do Mês, Valor Total
- Recent activity table
- Quick action buttons

### Measurement Entry
- Two-column layout: Left (obra details form), Right (locations grid)
- Beach/Norte/Torre/Adicionais inputs
- Auto-calculated total display
- Save/Cancel actions

### Daily Attendance
- Full-width table with horizontal scroll
- Filters: Date range, empresa, obra
- Export/print button in header
- Employee row entry with checkboxes per day
- Totals footer row

### Reports View
- Print-optimized layout (@media print rules)
- Header: Logo + Company info (side-by-side)
- Tables with borders for clarity
- Footer: Signatures and approval fields
- A4 page breaks respect

## Print Specifications
- White backgrounds, dark text
- Remove navigation, hide interactive elements
- Logo: Top-left, h-20
- Tables: Full borders, compact padding
- Font sizes: Slightly larger for readability
- Page margins: 1.5cm all sides

## Responsive Breakpoints
- Mobile (<768px): Stacked layout, collapsible sidebar, card-based tables
- Tablet (768px-1024px): Reduced sidebar, optimized table columns
- Desktop (>1024px): Full layout with all features visible

## Accessibility
- WCAG AA contrast ratios
- Keyboard navigation for all interactions
- Focus visible indicators (ring-2 ring-offset-2)
- Screen reader labels for icon-only buttons
- Form labels always visible

## Images
**Logo Usage**: LinkUp 3D logo provided
- Login page: Centered, h-16
- Sidebar: h-10, left-aligned
- Print header: h-20
- Format: PNG with transparency

No decorative images needed - this is a data-focused application where visual hierarchy comes from typography and spacing, not imagery.