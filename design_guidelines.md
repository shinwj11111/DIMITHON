# Design Guidelines: Campus Store Delivery App

## Design Approach
**Selected System:** Material Design 3 (Mobile-First)
**Justification:** This utility-focused e-commerce app prioritizes efficiency, learnability, and standard shopping patterns. Material Design's mobile-optimized components and established interaction patterns perfectly match the need for quick, intuitive ordering within a campus environment.

**Key Design Principles:**
- Speed and efficiency in ordering process
- Clear visual hierarchy for product information
- Touch-friendly mobile-first interface
- Familiar e-commerce patterns for instant usability

## Typography System

**Font Family:** Roboto (via Google Fonts CDN)

**Hierarchy:**
- Screen Titles: Roboto Medium, 24px (1.5rem)
- Section Headers: Roboto Medium, 20px (1.25rem)
- Product Names: Roboto Regular, 16px (1rem)
- Body Text: Roboto Regular, 14px (0.875rem)
- Prices: Roboto Medium, 18px (1.125rem)
- Helper Text: Roboto Regular, 12px (0.75rem)
- Button Labels: Roboto Medium, 14px (0.875rem)

## Layout System

**Spacing Primitives:** Tailwind units of 2, 4, 6, 8, 12, and 16
- Micro spacing (between related elements): p-2, gap-2
- Component internal padding: p-4
- Section spacing: py-6, py-8
- Screen padding: px-4, py-6
- Large gaps between major sections: gap-12, py-16

**Grid System:**
- Product list: Single column (w-full)
- Maximum content width: max-w-md (448px) centered for optimal mobile reading
- Full-width containers for app chrome (navigation, headers)

## Component Library

### Authentication Screens

**Login Screen:**
- Centered vertical layout with max-w-sm container
- Logo/App name at top (h-16, mb-12)
- "Sign in with Google" button: Full-width, h-12, rounded-lg, with Google icon
- Subtle helper text below button explaining first-time card registration (text-sm, mt-4)
- Safe area padding: px-4, py-8

**Card Registration Modal:**
- Overlay with backdrop blur
- Card form container: max-w-sm, rounded-2xl, p-6
- Input fields: h-12, rounded-lg, px-4, mb-4
- Card preview visual above form
- "Save Card" primary button: w-full, h-12, rounded-lg
- Material Design elevation: shadow-lg

### Bottom Navigation Bar

**Structure:**
- Fixed bottom position, w-full, h-16
- Two tabs: "Products" and "Profile"
- Icon + label combination (vertical stack)
- Icons: 24px (h-6 w-6) from Material Icons
- Labels: text-xs, mt-1
- Active state: Different visual treatment (no color specified)
- Safe bottom padding for mobile devices: pb-safe

### Product Catalog Screen

**Header:**
- Fixed top bar, h-14, px-4
- App name/logo left-aligned
- Cart icon button right-aligned (relative positioning for badge)
- Cart badge: Absolute positioned, rounded-full, min-w-5, h-5, text-xs

**Product List:**
- Vertical scroll container with pb-20 (space for bottom nav)
- Single column layout
- Product cards spacing: gap-4, px-4

**Product Card:**
- Full-width container
- Rounded-xl border
- Layout: Horizontal flex (image left, content right)
- Product image: w-24 h-24, rounded-l-xl, object-cover
- Content section: flex-1, p-4
- Product name: font-medium, text-base, mb-1
- Price: font-medium, text-lg
- Tap area: Full card is tappable
- Material Design elevation on press

### Product Detail Modal

**Structure:**
- Bottom sheet style modal sliding from bottom
- Rounded top corners: rounded-t-3xl
- Content padding: p-6
- Product image: w-full, h-48, rounded-xl, object-cover, mb-4
- Product info section: mb-6
  - Name: text-xl, font-medium, mb-2
  - Price: text-2xl, font-medium

**Quantity Selector:**
- Horizontal flex layout, items-center, gap-4, mb-6
- Minus button: w-10 h-10, rounded-full border
- Quantity display: text-xl, font-medium, min-w-12, text-center
- Plus button: w-10 h-10, rounded-full border
- Large touch targets for mobile

**Action Buttons:**
- "Add to Cart" button: w-full, h-12, rounded-xl, font-medium
- Close/Back button: Top-right, w-10 h-10, rounded-full

### Shopping Cart & Checkout

**Cart Summary Sheet:**
- Bottom sheet modal, max-h-3/4 screen
- Rounded top: rounded-t-3xl, p-6
- Header: "Cart" text-xl, font-medium, mb-4
- Cart items list: gap-3, mb-6
  - Item row: Horizontal flex, justify-between, py-3, border-b
  - Left: Product name + quantity (text-sm)
  - Right: Price (font-medium)
- Subtotal row: font-medium, text-lg, py-2
- "Proceed to Checkout" button: w-full, h-12, rounded-xl, mt-4

**Checkout Screen:**
- Full screen with top bar (h-14) containing back button
- Content padding: px-4, py-6
- "Order Summary" section: mb-8
  - Section header: text-xl, font-medium, mb-4
  - Items list with same formatting as cart
  - Total price: text-2xl, font-bold, py-4, border-t-2
- Payment method display: mb-6
  - Card icon and last 4 digits
  - Rounded container: rounded-lg, border, p-4
- "Place Order" button: w-full, h-12, rounded-xl, fixed bottom with safe padding

### Profile Tab

**Header:**
- Top section: px-4, py-6
- Profile icon: w-16 h-16, rounded-full, mb-3
- Google email: text-base, font-medium

**Information Cards:**
- Section spacing: gap-4, px-4
- Card containers: rounded-xl, border, p-4

**Payment Method Card:**
- Icon + card info horizontal layout
- "Card ending in ****" text
- Edit button: text-sm, right-aligned

**Purchase History:**
- Section header: text-lg, font-medium, px-4, mb-3
- History items: gap-3
  - Item container: rounded-xl, border, p-4
  - Date: text-xs, mb-2
  - Items summary: text-sm, mb-1
  - Total: font-medium, text-lg
- Empty state: Centered text with icon, py-12

## Interaction Patterns

**Tap Targets:**
- Minimum height: h-12 (48px) for all interactive elements
- Buttons: h-12, rounded-xl, px-6
- Icon buttons: w-10 h-10 minimum
- Full-width buttons on mobile: w-full

**Loading States:**
- Skeleton screens for product loading
- Spinner overlay for transactions
- Button disabled state with loading indicator

**Feedback:**
- Material Design ripple effects on all tappable surfaces
- Micro-interactions on quantity changes
- Success confirmation after order placement
- Toast notifications for cart additions

## Screen-Specific Layouts

**Full Screen Modals:** Login, Checkout
- Centered content with max-w-sm
- Consistent padding: px-4, py-8

**Bottom Sheets:** Product detail, Cart summary
- Slide up animation
- Drag handle at top
- Rounded top corners: rounded-t-3xl
- Max height constraints

**Scrollable Lists:** Products, Purchase history
- Bottom padding for navigation bar: pb-20
- Smooth scrolling behavior
- Pull-to-refresh on product list

## Images

**Product Images:** Required for each product card and detail view
- Card thumbnail: 96x96px, square crop
- Detail view: 16:9 aspect ratio, full width
- Object-fit: cover to maintain aspect ratio
- Quality: Optimized for mobile bandwidth

**Profile Avatar:** Google account photo
- Circular crop, 64x64px
- Fallback to initial letter if no photo

**Empty States:** Simple illustrations for:
- Empty cart
- No purchase history
- Card registration success

This mobile-first design prioritizes speed, clarity, and familiar e-commerce patterns to create an efficient campus delivery experience.