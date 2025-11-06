# Vibe Commerce - Full-Stack E-Commerce Application

A professional, feature-rich shopping cart application built for Vibe Commerce screening. This project showcases modern web development practices with complete JWT authentication, email notifications, wishlist functionality, and an elegant user interface.

## 🌟 Standout Features

### 1. **JWT Authentication** 🔐
- Secure user registration and login system
- Password hashing with bcryptjs
- JWT token-based authentication
- Protected routes and API endpoints
- Persistent login sessions
- User profile management

### 2. **Email Confirmation System** 📧
- Professional order confirmation emails using **Resend API**
- Beautiful HTML email templates with gradient headers
- Detailed order summary with itemized list
- Trust badges for security and fast shipping
- Error handling with graceful fallbacks

### 3. **Similar Products Recommendation** 🔄
- Intelligent product recommendations on detail pages
- Category-based similarity matching
- Fallback to random products for variety
- Beautiful grid layout with smooth navigation
- Increases user engagement and cross-selling

### 4. **Wishlist Functionality** ❤️
- Save products for later viewing
- Dedicated wishlist page with beautiful grid layout
- Heart icon on every product card with animation
- Add to cart directly from wishlist
- Persistent wishlist storage per user

### 5. **Advanced Search & Filtering** 🔍
- Real-time product search by name and description
- Category-based filtering
- Clean, modern search interface with clear button
- Combined search + category filtering
- "No results" state with helpful messaging

### 6. **Professional UI/UX Design** 🎨
- **Trustworthy blue gradient theme** (#1e3a8a to #3b82f6)
- Smooth animations and transitions
- Responsive design for all devices
- Hover effects and visual feedback
- Clean, modern card-based layouts
- Professional hero section

### 7. **Complete Shopping Experience** 🛒
- Full cart management (add, update quantity, remove)
- Real-time cart updates
- Stock availability indicators
- Price calculations with subtotal and total
- Smooth checkout flow
- Order receipt modal with order summary

### 8. **React Router Integration** 🗺️
- Dedicated pages for Home, Cart, Wishlist, Product Details, Checkout, Login, Register
- Clean URL structure
- Navigation between pages
- Product detail pages with similar products
- Continue shopping redirects to home

## 🛠️ Tech Stack

### Backend
- **Node.js** & **Express.js** - REST API server
- **MongoDB** with **Mongoose** - Database and ODM
- **JWT (jsonwebtoken)** - Authentication tokens
- **bcryptjs** - Password hashing
- **Resend** - Email service integration
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment configuration

### Frontend
- **React 18** - UI framework
- **React Router DOM** - Client-side routing
- **Axios** - HTTP client with interceptors
- **CSS3** - Custom styling with gradients and animations
- **LocalStorage** - Token and user persistence

## 📁 Project Structure

```
Nexora/
├── backend/
│   ├── models/
│   │   ├── User.js          # User authentication model
│   │   ├── Product.js       # Product schema
│   │   ├── Cart.js          # Cart schema (user-linked)
│   │   ├── Order.js         # Order schema
│   │   └── Wishlist.js      # Wishlist schema (user-linked)
│   ├── routes/
│   │   ├── auth.js          # Authentication endpoints
│   │   ├── products.js      # Product CRUD + similar products
│   │   ├── cart.js          # Cart management endpoints
│   │   ├── checkout.js      # Checkout and order creation
│   │   └── wishlist.js      # Wishlist endpoints
│   ├── middleware/
│   │   └── auth.js          # JWT authentication middleware
│   ├── services/
│   │   └── emailService.js  # Resend email integration
│   ├── seed.js              # Database seeding script
│   ├── server.js            # Express app configuration
│   └── .env                 # Environment variables
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Header.js/css           # Navigation with auth
    │   │   ├── ProductCard.js/css      # Product card with wishlist
    │   │   ├── ProductsGrid.js/css     # Product grid layout
    │   │   ├── Cart.js/css             # Cart component
    │   │   ├── CheckoutForm.js/css     # Checkout form
    │   │   ├── ReceiptModal.js/css     # Order confirmation
    │   │   └── SearchBar.js/css        # Search component
    │   ├── pages/
    │   │   ├── HomePage.js/css         # Home with search & filters
    │   │   ├── CartPage.js/css         # Cart page
    │   │   ├── WishlistPage.js/css     # Wishlist page
    │   │   ├── ProductDetailPage.js/css # Product + similar products
    │   │   ├── LoginPage.js            # Login form
    │   │   ├── RegisterPage.js         # Registration form
    │   │   └── AuthForm.css            # Shared auth styles
    │   ├── services/
    │   │   └── api.js                  # API service with auth
    │   └── App.js                      # Main app with routes
    └── package.json
```

## 🚀 Setup & Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (running locally or MongoDB Atlas)
- Resend API key (get free at https://resend.com)

### Backend Setup

1. Navigate to backend directory:
```powershell
cd backend
```

2. Install dependencies:
```powershell
npm install
```

3. Create `.env` file:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/vibe-commerce
NODE_ENV=development
JWT_SECRET=vibe_commerce_jwt_secret_key_2025_secure_random_string

# Email Configuration (OPTIONAL - see note below)
RESEND_API_KEY=your_resend_api_key_here
FROM_EMAIL=onboarding@resend.dev
```

> **📧 Email Configuration Note:**
> - Emails are **OPTIONAL** - the app works perfectly without them
> - If you don't configure Resend API key, orders will still be created successfully
> - Emails will be automatically skipped with a console message
> - To enable emails: Get a free API key from [resend.com](https://resend.com/api-keys)
> - To disable emails: Remove or comment out the `RESEND_API_KEY` line

4. Seed the database:
```powershell
node seed.js
```

5. Start the server:
```powershell
node server.js
```

Server runs on `http://localhost:5000`

### Frontend Setup

1. Navigate to frontend directory:
```powershell
cd frontend
```

2. Install dependencies:
```powershell
npm install
```

3. Start the development server:
```powershell
npm start
```

Frontend runs on `http://localhost:3000`

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)

### Products
- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get product by ID
- `GET /api/products/:id/similar` - Get similar products

### Cart (Optional Auth)
- `GET /api/cart` - Get user's cart
- `POST /api/cart` - Add item to cart
- `PUT /api/cart/:itemId` - Update item quantity
- `DELETE /api/cart/:itemId` - Remove item from cart
- `DELETE /api/cart` - Clear entire cart

### Wishlist (Optional Auth)
- `GET /api/wishlist` - Get user's wishlist
- `POST /api/wishlist` - Add item to wishlist
- `DELETE /api/wishlist/:productId` - Remove item from wishlist

### Checkout
- `POST /api/checkout` - Process order and send email confirmation

## ✨ Key Features Implemented

### 1. JWT Authentication
- User registration with validation
- Secure password hashing (bcryptjs)
- JWT token generation (7-day expiry)
- Token storage in localStorage
- Axios interceptors for automatic token inclusion
- Protected API routes
- Login/logout functionality
- User display in header

### 2. Similar Products
- Category-based product recommendations
- Shows up to 4 similar products per product detail page
- Fallback to random products if insufficient category matches
- Click to navigate to similar product
- Beautiful grid layout with hover effects

### 3. Email Confirmation
- Integration with Resend API
- Professional HTML email templates
- Order details with itemized list
- Gradient headers matching brand theme
- Error handling and fallbacks

### 4. Search & Filter
- Real-time search across product names and descriptions
- Category filtering with active state highlighting
- Combined search + filter functionality
- Responsive search bar with clear button

### 5. Wishlist System
- Backend API for wishlist management
- Beautiful wishlist page with grid layout
- Heart icon on product cards with animation
- Add to cart from wishlist
- Remove items with confirmation

### 6. Professional Theme
- Trust-building blue gradient (#1e3a8a to #3b82f6)
- Consistent color scheme across all pages
- Smooth animations and transitions
- Professional hero section
- Card-based layouts

## 🎯 User Flow

### Guest User Flow:
1. Browse products on home page
2. Search and filter products
3. View product details with similar products
4. Add to cart or wishlist (guest mode)
5. Manage cart
6. Checkout (without login)
7. Receive order confirmation email

### Authenticated User Flow:
1. **Register/Login** - Create account or sign in
2. Browse products with personalized experience
3. Save items to wishlist (persisted per user)
4. View cart (linked to user account)
5. Checkout with saved information
6. Receive confirmation email
7. Logout when done

## 🔐 Security Features

- **Password Hashing**: bcryptjs with salt rounds
- **JWT Tokens**: Secure token-based authentication
- **Environment Variables**: Sensitive data protection
- **CORS Configuration**: Controlled cross-origin access
- **Input Validation**: Server-side validation
- **Error Handling**: Graceful error responses

## 🎨 Design Highlights

- **Color Palette**: Blue gradient theme (#1e3a8a to #3b82f6) for trust
- **Typography**: Clean, modern fonts with proper hierarchy
- **Spacing**: Consistent padding and margins (8px grid)
- **Animations**: Smooth transitions (0.3s ease)
- **Icons**: SVG icons for crisp display
- **Responsive**: Mobile-first approach with breakpoints

## 📱 Responsive Breakpoints

- **Desktop**: > 768px (full features)
- **Tablet**: 481px - 768px (adjusted layouts)
- **Mobile**: ≤ 480px (single column, touch-optimized)

## 🚀 Competitive Advantages

1. **JWT Authentication** - Professional user management system
2. **Similar Products** - Increases engagement and sales
3. **Email Integration** - Professional order confirmations
4. **Wishlist Feature** - Enhanced user retention
5. **Advanced Search** - Improved product discovery
6. **Professional Design** - Trust-building theme
7. **Complete Features** - All essential e-commerce functionality
8. **Clean Code** - Well-organized, maintainable architecture
9. **Security** - Industry-standard authentication
10. **Scalable** - Ready for production deployment

## 📝 Future Enhancement Ideas

- Password reset functionality
- Social authentication (Google, Facebook)
- User profile editing
- Order history page with tracking
- Product reviews and ratings
- Recently viewed products
- Related products recommendations
- Payment gateway integration (Stripe)
- Admin dashboard
- Inventory management
- Discount codes and promotions
- Email verification
- Two-factor authentication

## 👨‍💻 Developer Notes

### Why This Stands Out:

1. **JWT Authentication** - Professional user management, not just mock users
2. **Similar Products** - Shows understanding of recommendation systems
3. **Email Confirmation** - Production-ready order notifications
4. **Wishlist** - User engagement and retention features
5. **Search/Filter** - Complex state management
6. **Professional UI** - Not just functional, visually impressive
7. **Clean Code** - Component-based, service layer architecture
8. **Security** - Industry-standard practices

### Technical Highlights:

- React hooks (useState, useEffect, useMemo)
- React Router for navigation
- Axios interceptors for auth
- JWT token management
- MongoDB with Mongoose
- Express.js middleware patterns
- Service layer architecture
- Component composition
- CSS animations and transitions
- Password hashing and security

## 🤝 Contributing

This is a screening project for Vibe Commerce internship. For questions or suggestions, please reach out.

## 📄 License

This project is created for educational and screening purposes.

---

**Built with ❤️ for Vibe Commerce Screening**

*Featuring: JWT Authentication, Email Notifications, Similar Products, Wishlist, Search & Filter, and Professional UI/UX*
