🌿 LeafBasket - Project Documentation
1. Project Overview
LeafBasket is a modern, responsive e-commerce web application dedicated to bringing nature indoors. It provides users with a seamless platform to browse, select, and purchase indoor plants, outdoor plants, and gardening accessories.

Target Audience
Plant enthusiasts, urban dwellers looking to decorate their homes with greenery, and anyone seeking a streamlined online plant shopping experience.

Tech Stack
Structure: Semantic HTML5 for accessible and well-organized page architecture.
Styling: Tailwind CSS utilized via both pre-processed stylesheets (`output.css`) and dynamic CDN scripts. Custom themes are extended directly in the `<head>` (e.g., configuring custom `brandGreen: '#2d5a27'`).
Assets: Unsplash for high-quality, nature-themed placeholder imagery, and local custom branding assets (e.g., `LeafBasket.png`, `LeafBasket text-logo.png`). Lucide icons are referenced for feature highlights.
Design Approach: Mobile-first, responsive flexbox and CSS grid layouts ensuring cross-device compatibility from mobile viewports up to large desktop monitors.
2. Global Design System & Theming
The project utilizes a consistent design system to build trust and brand recognition.

Color Palette:
Primary Brand Color: LeafBasket Green (Hex codes `#78b032`, `#2d5a27` / Tailwind classes `text-green-800`, `bg-brandGreen`) - Used for primary actions, logos, and brand emphasis.
Backgrounds: Light Gray (bg-gray-50) for a clean, distraction-free canvas, and pure White (bg-white) for content cards.
Accents: Soft greens (bg-green-50, bg-green-100) for secondary buttons and highlight areas.
Typography: Clean, sans-serif font family prioritizing readability. Heavy font weights (`font-bold`, `font-semibold`) and oversized text (`text-8xl`, `text-9xl`) are strategically used for impactful hero statements.
UI Components:
Cards: Soft shadows (`shadow-sm`, `shadow-lg`), heavily rounded corners (`rounded-2xl`, `rounded-3xl`), and subtle hover transformations (`hover:shadow-md`, `hover:shadow-lg transition`).
Buttons & Inputs: Fully rounded pill-shapes (`rounded-full`) for global CTAs. Forms use rounded rectangles (`rounded-xl` and `rounded-lg`) combined with focus states that trigger a green outline (`focus:ring-2 focus:ring-brandGreen` or `focus:ring-[#78b032]`), ensuring clear interactive user feedback.
Layout Constraints: Centered content wrappers utilizing `max-w-7xl` (1280px) for general browsing pages and constrained widths (`max-w-5xl`, `max-w-md`) for focused tasks like checkout and authentication to maintain readability.
Navigation: A sticky top navigation bar (`sticky top-0 z-50 bg-white shadow-sm`) ensures immediate access to primary routes (Home, Shop, About, Login) and includes a branded logo lockup.
3. Page-by-Page Documentation
A. Landing Page (hero.html)
The entry point of the application, designed to immediately captivate the user and drive sales.

Hero Banner: A 720px tall section featuring a massive typography block ("Bring Nature Indoors") alongside a large nature-themed background image (`bg-[url('/images/hero-background.png')]`) and a primary "Shop Now" CTA routed to the cart.
Featured Plants Grid: A highly responsive grid (`grid-cols-1 sm:grid-cols-2 lg:grid-cols-4`) displaying 16 top-selling plants (e.g., Monstera, Snake Plant, Aloe Vera). Each card is an encapsulated flex-column component containing an image, title, price, and a localized "Add" button.
Category Navigation: A 3-column grid layout allowing users to visually filter by "Indoor Plants", "Outdoor Plants", and "Pots".
Value Propositions: Three distinct pillars explaining why users should choose LeafBasket (Sustainable Sourcing, Safe Delivery, and Plant Care Expert), represented by circular icon wrappers.
Global Footer: A deep green (`bg-green-900`) fat-footer containing brand messaging, quick links, customer service FAQ, and an integrated newsletter subscription input form.

B. User Authentication Flow
A frictionless, secure-feeling identity management module.

Container Architecture: All authentication pages utilize a full-screen, centered flexbox layout (`min-h-screen flex items-center justify-center bg-gray-50`) holding a restrained width card (`max-w-md` or `max-w-sm`) to keep the user's focus solely on the forms.
Login (`login.html`): Form capturing Email and Password. Includes a native HTML checkbox for "Remember Me" and direct routing to the forgot password and registration pages.
Register (`register.html`): Onboarding form capturing Full Name, Email, Password, Confirm Password, and a mandatory Terms & Conditions checkbox (`required` attribute utilized for native HTML5 validation).
Forgot Password (`forgot.html`): A minimalist recovery view requesting the user's email address. It features contextual helper text guiding the user on the expected outcome.

C. Shopping Cart (cart.html)
Designed to increase Average Order Value (AOV) and create urgency.

Urgency Banner: A sticky sub-header below the main navigation alerting the user that items are reserved for 10 minutes, supplemented with a customer support hotline.
Gamification/Progress Bar: A dynamic-looking visual progress bar (styled at 75% width) showing the user how close they are to unlocking conditional perks like "FREE SHIPPING" and "3% EXTRA CASHBACK".
Cart Line Items: A detailed list view structured using Flexbox. It displays a thumbnail image, product title, metadata (Color/Size), inventory status ("In Stock (12 Pcs)"), unit price, and a quantity adjustment control block (`-` / `+`).
Action Row: Bottom anchors routing the user back to the shop (`hero.html`) or forward to the payment gateway (`shipping-address.html`).

D. Checkout & Shipping (shipping-address.html)
A streamlined, one-page checkout experience designed to reduce cart abandonment.

Layout Architecture: An asymmetrical 3-column CSS Grid (`grid lg:grid-cols-3`). The main form spans 2 columns (`lg:col-span-2`), while the Order Summary acts as a sticky-style sidebar in the remaining column.
Delivery Details: A multi-row form capturing user logistics. Responsive inner grids (`grid-cols-1 md:grid-cols-2` and `md:grid-cols-3`) are used to efficiently pack fields like First Name/Last Name and City/State/Zip side-by-side on larger screens.
Payment Methods: Interactive, selectable payment options:
  - Credit/Debit Card: The default expanded state. Accepts Card Number, MM/YY, CVC, and Name on Card. Includes SVG trust badges (Visa, Mastercard) to boost conversion confidence.
  - UPI: Specialized option catering to localized digital payments (GPay, PhonePe, Paytm).
  - Cash on Delivery (COD): Alternative option for users preferring physical payment on receipt.
Order Summary: A `h-fit` side-panel detailing the financial breakdown (Subtotal, Shipping charge, and bolded Total), paired with the final, prominent "Place Order" CTA.

4. Navigation Flow (User Journey)
Discovery: User lands on hero.html -> Browses Featured Plants.
Conversion: User clicks "Add" -> Navigates to cart.html to review items.
Authentication (Optional step based on flow): User clicks "Login" -> login.html -> (If new) register.html.
Checkout: From the Cart, user proceeds to shipping-address.html -> Fills in details -> Places Order.

5. Future Technical Enhancements (Next Steps)
While the UI and design system are currently complete in HTML/CSS, the application requires the following implementations to become fully functional:
- State Management: JavaScript logic needs to be integrated to handle dynamic cart item quantities, calculate subtotal/total algorithms, and manage "Add to cart" button click events.
- Backend Integration: Form endpoints (e.g., `<form action="...">`) currently simulate navigation but must be connected to authentication and payment processing APIs (like Stripe or Razorpay for the UPI/Card modules).
- Componentization: If scaling the app, refactoring the repetitive HTML (like the 16 featured plant cards) into reusable components (using React, Vue, or a templating engine) is highly recommended.

Tips for Presentation Delivery:
Visuals: Take screenshots of the rendered HTML pages in a browser to put alongside these bullet points on your presentation slides.
Live Demo: If possible, host these files locally and click through the application (e.g., Home -> Cart -> Checkout) to demonstrate the user flow in real-time.