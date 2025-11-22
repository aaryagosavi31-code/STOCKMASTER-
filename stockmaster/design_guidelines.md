# Inventory Management System (IMS) - Design Guidelines

## Design Approach
**Selected Approach:** Design System (Hybrid of Fluent Design + Linear)
**Rationale:** This is a utility-focused, data-heavy productivity application requiring clarity, efficiency, and support for complex analytics. Drawing from Fluent Design's enterprise patterns and Linear's modern aesthetic for clean data presentation.

## Core Design Principles
1. **Information Clarity:** Data must be scannable and hierarchically organized
2. **Efficient Workflows:** Minimize clicks for common warehouse operations
3. **Visual Data Density:** Support dense information displays while maintaining readability
4. **Responsive Analytics:** Charts and tables adapt seamlessly across devices

---

## Typography System

**Font Family:** Inter (via Google Fonts CDN)
- Primary: Inter (400, 500, 600, 700)

**Hierarchy:**
- Page Titles: text-2xl font-semibold (24px)
- Section Headers: text-xl font-semibold (20px)
- Card/Component Titles: text-lg font-medium (18px)
- Body Text: text-base font-normal (16px)
- Secondary/Meta Text: text-sm font-normal (14px)
- Labels/Captions: text-xs font-medium (12px uppercase tracking-wide)
- Data Values (in tables/charts): text-sm font-medium (14px)

---

## Layout System

**Spacing Primitives:** Tailwind units of 2, 4, 6, 8, 12, 16
- Component padding: p-4, p-6, p-8
- Section gaps: gap-4, gap-6, gap-8
- Margins: m-4, m-6, m-8
- Icon spacing: mr-2, ml-2

**Grid Structure:**
- Dashboard: 12-column grid (grid-cols-12)
- Analytics cards: 3-column on desktop (lg:grid-cols-3), 1-column mobile
- Data tables: Full-width with horizontal scroll on mobile
- Sidebar navigation: 240px fixed width (w-60)

**Container Widths:**
- Main content: max-w-7xl mx-auto px-6
- Modals/Dialogs: max-w-2xl for forms, max-w-4xl for analytics

---

## Component Library

### Navigation
**Sidebar (Desktop):**
- Fixed left sidebar (w-60)
- Logo/brand at top (h-16)
- Navigation items: py-3 px-4 with icon + label
- Active state: subtle background treatment
- User profile section at bottom

**Top Bar:**
- Fixed header (h-16) with shadow
- Breadcrumb navigation (text-sm)
- Search bar (w-96 max)
- Notification bell + user avatar (right-aligned)

**Mobile Navigation:**
- Bottom tab bar with 4-5 primary actions
- Hamburger menu for secondary navigation

### Dashboard Components

**Stat Cards:**
- Grid layout (grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6)
- Card structure: p-6 rounded-lg border
- Large number display (text-3xl font-bold)
- Label below (text-sm)
- Trend indicator with icon (arrow up/down)
- Compact size: h-32

**Chart Containers:**
- Standard card wrapper: p-6 rounded-lg border
- Chart title (text-lg font-semibold mb-4)
- Chart height: h-80 for primary charts, h-64 for secondary
- Use Chart.js or Recharts via CDN
- Include legend and axis labels

**Charts to Include:**
1. Line chart: Stock levels over time
2. Bar chart: Category-wise inventory distribution
3. Pie chart: Stock status breakdown (In Stock, Low Stock, Out of Stock)
4. Horizontal bar: Top 10 moving items

### Data Tables

**Structure:**
- Sticky header row (sticky top-0)
- Alternating row treatment for scannability
- Row height: h-16 for comfortable touch targets
- Cell padding: px-4 py-3
- Right-align numerical columns
- Action buttons column (right-most, w-32)

**Features:**
- Search input (top-right, w-64)
- Filter dropdowns (inline above table)
- Sort indicators in headers (chevron icons)
- Pagination controls (bottom, justify-between)
- Row selection checkboxes (left column, w-12)
- Empty state: centered message with icon (h-64)

### Forms & Inputs

**Form Layout:**
- Two-column grid on desktop (grid-cols-2 gap-6)
- Single column on mobile
- Label above input (text-sm font-medium mb-2)
- Input height: h-10
- Input padding: px-3
- Border: border rounded-md
- Focus state: ring treatment

**Input Types:**
- Text/Number: Standard input (w-full)
- Select dropdowns: Custom styled (h-10)
- Date pickers: Native input type="date"
- File upload: Bordered dashed area (h-32)

**Buttons:**
- Primary: px-4 py-2 rounded-md font-medium
- Secondary: Same with border treatment
- Icon-only: w-10 h-10 rounded-md
- Button groups: gap-2

### Modals & Dialogs

**Modal Structure:**
- Overlay: backdrop-blur-sm
- Modal card: rounded-lg shadow-xl (max-w-2xl)
- Header: px-6 py-4 border-b (h-16)
- Body: px-6 py-4 (max-h-96 overflow-y-auto)
- Footer: px-6 py-4 border-t (justify-end gap-3)

**Alert System:**
- Toast notifications (top-right, w-96)
- Success/warning/error indicators with icons
- Auto-dismiss after 4s
- Stack multiple toasts (gap-2)

### Stock Management UI

**Inventory Card:**
- Grid item: aspect-square on desktop
- Product image placeholder (h-48 bg-gray-100)
- SKU and name (truncate)
- Stock quantity badge (absolute top-2 right-2)
- Action buttons at bottom (mt-auto)

**Stock Level Indicators:**
- Progress bar representation (h-2 rounded-full)
- Threshold markers at 20% and 50%
- Quantity number (text-sm font-medium)

**Transaction History:**
- Timeline layout (border-l-2 pl-4)
- Entry: pb-6 relative
- Timestamp (text-xs)
- Action type with icon
- User who performed action

---

## Icons
**Library:** Heroicons (via CDN)
- Navigation: 24px outline icons
- Inline actions: 20px solid icons
- Status indicators: 16px solid icons
- Chart legends: 12px solid icons

**Key Icons:**
- Dashboard: ChartBarIcon
- Inventory: CubeIcon
- Transactions: ArrowsRightLeftIcon
- Alerts: BellIcon
- Users: UserGroupIcon
- Search: MagnifyingGlassIcon
- Filter: FunnelIcon
- Export: ArrowDownTrayIcon

---

## Responsive Breakpoints
- Mobile: < 768px (single column, bottom nav)
- Tablet: 768px - 1024px (2-column grids)
- Desktop: > 1024px (full layout with sidebar)

**Mobile Optimizations:**
- Hide sidebar, use bottom navigation
- Stack dashboard cards vertically
- Horizontal scroll for wide tables
- Simplified chart displays
- Bottom sheet modals instead of centered

---

## Images
No hero images required. This is a functional dashboard application.

**Product/Inventory Images:**
- Placeholder: 200x200px square thumbnails
- Location: In inventory cards and detail modals
- Treatment: rounded corners, border