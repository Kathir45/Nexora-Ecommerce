# 🛒 Vibe Commerce - AI-Powered E-Commerce Platform

A modern, full-stack e-commerce application built with the MERN stack, featuring an intelligent AI shopping assistant powered by Google Gemini AI.

![MERN Stack](https://img.shields.io/badge/Stack-MERN-green)
![React](https://img.shields.io/badge/React-18.0-blue)
![Node](https://img.shields.io/badge/Node-16+-green)
![MongoDB](https://img.shields.io/badge/MongoDB-Latest-green)
![AI](https://img.shields.io/badge/AI-Gemini-purple)

---

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#%EF%B8%8F-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [API Endpoints](#-api-endpoints)
- [AI Shopping Assistant](#-ai-shopping-assistant)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)

---

## ✨ Features

### 🛍️ Shopping Experience
- **30+ Product Catalog** - Diverse products across Electronics, Fashion, Home & Living, Sports & Outdoors, and Books & Media
- **Advanced Search** - Real-time search suggestions with product images and prices
- **Smart Pagination** - Browse products efficiently with 12 items per page
- **Category Filtering** - Filter products by category for quick navigation
- **Product Details** - Comprehensive product pages with images, descriptions, pricing, and stock status
- **Similar Products** - AI-recommended similar items on each product page
- **Recently Viewed** - Track and display last 10 viewed products

### 🤖 AI Shopping Assistant
- **Google Gemini AI Integration** - Intelligent product recommendations
- **Natural Language Queries** - Ask questions like "suggest low budget headphones under $50"
- **Contextual Responses** - Maintains conversation history for better recommendations
- **Clickable Product Links** - Direct navigation to recommended products
- **Quick Actions** - Pre-defined suggestion buttons for common queries
- **Clear Chat** - Reset conversation anytime

### 🔐 Authentication & User Management
- **JWT Authentication** - Secure token-based authentication
- **User Registration & Login** - Create accounts with email and password
- **Password Security** - Bcrypt hashing for secure password storage
- **Protected Routes** - Middleware-protected API endpoints
- **Session Persistence** - Automatic login with stored tokens
- **User Profile** - View and manage account information

### 🛒 Shopping Cart & Checkout
- **Guest Cart Support** - Add items without logging in
- **Cart Persistence** - Save cart items in localStorage for guests
- **Cart Migration** - Automatic cart merge when guests log in
- **Real-time Updates** - Instant cart total and item count updates
- **Quantity Management** - Increase/decrease quantities or remove items
- **Stock Validation** - Prevent adding out-of-stock items
- **Secure Checkout** - Login-required checkout process
- **Order Confirmation** - Email receipts with order details (via Resend API)

### 💝 Wishlist
- **Save Favorites** - Add products to wishlist with heart icon
- **Persistent Storage** - Wishlist saved to database for logged-in users
- **Easy Management** - View and remove items from dedicated wishlist page
- **Quick Actions** - Move items from wishlist to cart

### ⭐ Reviews & Ratings
- **Product Reviews** - Write and read product reviews
- **Star Ratings** - 5-star rating system with visual feedback
- **Average Ratings** - Calculated average rating display
- **Review Comments** - Detailed feedback from customers
- **Helpful Voting** - Mark reviews as helpful (like system)
- **User Attribution** - See who wrote each review

### 📦 Order Management
- **Order History** - View all past orders
- **Order Tracking** - Track order status (Pending, Processing, Shipped, Delivered)
- **Order Details** - Complete breakdown of items, quantities, and totals
- **Customer Information** - Stored shipping details
- **Email Notifications** - Professional order confirmation emails
- **Order Numbers** - Unique identifiers for each order

### 📱 Responsive Design
- **Mobile-First Approach** - Optimized for all screen sizes
- **Hamburger Menu** - Smooth slide-in navigation for mobile
- **Touch-Optimized** - Easy interaction on touch devices
- **Breakpoints** - 992px (tablet), 768px (mobile), 480px (small mobile)
- **Adaptive Layouts** - Grid layouts adjust based on screen size
- **Smooth Animations** - 60fps transitions and effects

### 🎨 Modern UI/UX
- **Professional Design** - Blue-to-purple gradient theme
- **Card-Based Layouts** - Clean, organized product displays
- **Hover Effects** - Interactive feedback on all clickable elements
- **Loading States** - Skeleton screens and spinners
- **Error Handling** - User-friendly error messages
- **Toast Notifications** - Success/error alerts
- **Modal Dialogs** - Order confirmations and alerts

### ⚡ Performance Optimizations
- **Debounced Search** - Reduced API calls (300ms delay)
- **Lazy Loading** - Components load on demand
- **Client-Side Caching** - localStorage for guest data
- **Efficient Queries** - Optimized MongoDB queries with indexing
- **Image Optimization** - Responsive images from Unsplash
- **Code Splitting** - React Router lazy loading

---

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library with Hooks
- **React Router DOM 6** - Client-side routing
- **Axios** - HTTP client for API calls
- **CSS3** - Modern styling with Flexbox & Grid
- **LocalStorage** - Client-side data persistence

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **JWT (jsonwebtoken)** - Authentication tokens
- **Bcryptjs** - Password hashing
- **CORS** - Cross-origin resource sharing
- **Dotenv** - Environment variable management

### AI Integration
- **Google Gemini AI** - Generative AI (gemini-2.0-flash-exp)
- **@google/generative-ai** - Official Gemini SDK

### Additional Services
- **Resend** - Transactional email service
- **Unsplash** - Product images

---

## 📁 Project Structure

```
Nexora/
├── backend/
│   ├── models/
│   │   ├── User.js           # User schema
│   │   ├── Product.js        # Product schema
│   │   ├── Cart.js           # Shopping cart schema
│   │   ├── Order.js          # Order schema
│   │   ├── Wishlist.js       # Wishlist schema
│   │   └── Review.js         # Product review schema
│   ├── routes/
│   │   ├── auth.js           # Authentication routes
│   │   ├── products.js       # Product CRUD & search
│   │   ├── cart.js           # Cart management
│   │   ├── checkout.js       # Checkout & orders
│   │   ├── wishlist.js       # Wishlist operations
│   │   ├── reviews.js        # Product reviews
│   │   └── ai.js             # AI assistant endpoints
│   ├── middleware/
│   │   └── auth.js           # JWT verification
│   ├── services/
│   │   └── emailService.js   # Email sending with Resend
│   ├── .env                  # Environment variables
│   ├── server.js             # Express app setup
│   ├── seedProducts.js       # Database seeding script
│   └── package.json
│
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── Header.js & .css        # Navigation header
│   │   │   ├── ProductCard.js & .css   # Product display card
│   │   │   ├── ProductsGrid.js & .css  # Product grid layout
│   │   │   ├── CheckoutForm.js & .css  # Checkout form
│   │   │   ├── ProductReviews.js       # Reviews section
│   │   │   ├── RecentlyViewed.js       # Recently viewed products
│   │   │   └── AIAssistant.js & .css   # AI chatbot
│   │   ├── pages/
│   │   │   ├── HomePage.js & .css           # Home page
│   │   │   ├── ProductDetailPage.js & .css  # Product details
│   │   │   ├── CartPage.js & .css           # Shopping cart
│   │   │   ├── WishlistPage.js & .css       # Wishlist page
│   │   │   ├── OrdersPage.js & .css         # Order history
│   │   │   ├── SearchResultsPage.js & .css  # Search results
│   │   │   ├── LoginPage.js                 # Login form
│   │   │   ├── RegisterPage.js              # Registration form
│   │   │   └── AuthForm.css                 # Auth form styles
│   │   ├── services/
│   │   │   └── api.js              # API service layer
│   │   ├── App.js                  # Main app component
│   │   ├── App.css                 # Global styles
│   │   ├── index.js                # React entry point
│   │   └── index.css               # Base styles
│   └── package.json
│
├── README.md                   # This file
├── AI_ASSISTANT.md            # AI feature documentation
├── ASSIGNMENT_COMPLETION_NOTE.md  # Submission note
└── .env.example               # Environment template
```

---

## 🚀 Installation

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### 1. Clone the Repository
```bash
git clone <repository-url>
cd Nexora
```

### 2. Backend Setup
```bash
cd backend
npm install
```

Create a `.env` file:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/vibe-commerce
JWT_SECRET=your_super_secret_jwt_key_change_this_in_production
RESEND_API_KEY=your_resend_api_key_optional
GEMINI_API_KEY=your_gemini_api_key
```

Seed the database with products:
```bash
npm run seed
```

Start the backend server:
```bash
npm start
# or for development
npm run dev
```

### 3. Frontend Setup
```bash
cd ../frontend
npm install
```

Start the frontend:
```bash
npm start
```

The application will open at `http://localhost:3000`

---

## 🔧 Environment Variables

### Backend (.env)

| Variable | Description | Required |
|----------|-------------|----------|
| `PORT` | Server port (default: 5000) | Yes |
| `MONGODB_URI` | MongoDB connection string | Yes |
| `JWT_SECRET` | Secret key for JWT tokens | Yes |
| `RESEND_API_KEY` | Resend API key for emails | No |
| `GEMINI_API_KEY` | Google Gemini AI API key | Yes (for AI) |

### Getting API Keys

**Gemini API Key:**
1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Click "Get API Key"
3. Create new project or use existing
4. Copy the generated key

**Resend API Key (Optional):**
1. Visit [Resend](https://resend.com)
2. Sign up for free account
3. Go to API Keys section
4. Create new key and copy it

---

## 📡 API Endpoints

### Authentication
```
POST   /api/auth/register     # Register new user
POST   /api/auth/login        # Login user
GET    /api/auth/me           # Get current user (protected)
```

### Products
```
GET    /api/products                    # Get all products (with pagination)
GET    /api/products/search?q=query     # Search products
GET    /api/products/:id                # Get single product
GET    /api/products/:id/similar        # Get similar products
```

### Cart
```
GET    /api/cart              # Get cart items
POST   /api/cart              # Add item to cart
PUT    /api/cart/:id          # Update cart item quantity
DELETE /api/cart/:id          # Remove item from cart
POST   /api/cart/merge        # Merge guest cart with user cart
```

### Checkout & Orders
```
POST   /api/checkout          # Create order (protected)
GET    /api/checkout/orders   # Get user orders (protected)
```

### Wishlist
```
GET    /api/wishlist          # Get wishlist items
POST   /api/wishlist          # Add item to wishlist
DELETE /api/wishlist/:id      # Remove item from wishlist
```

### Reviews
```
GET    /api/reviews/:productId      # Get product reviews
POST   /api/reviews                 # Add review (protected)
POST   /api/reviews/:id/helpful     # Mark review as helpful
```

### AI Assistant
```
POST   /api/ai/chat                 # Chat with AI assistant
GET    /api/ai/suggestions          # Get product suggestions
```

---

## 🤖 AI Shopping Assistant

The AI Shopping Assistant is powered by Google Gemini AI and provides intelligent product recommendations based on natural language queries.

### Features
- **Natural Language Understanding** - Ask questions in plain English
- **Contextual Responses** - Remembers conversation history
- **Product Recommendations** - Suggests 1-3 relevant products
- **Clickable Links** - Direct navigation to products
- **Budget Awareness** - Understands price constraints
- **Category Filtering** - Suggests from specific categories

### Example Queries
```
"Show me headphones under $50"
"I need a laptop for gaming"
"Suggest wireless earbuds with good battery"
"What's the best smartphone for photography?"
"Find me running shoes in blue color"
```

### How It Works
1. User sends query via chat interface
2. Backend fetches current product catalog
3. Gemini AI analyzes query with product context
4. AI returns personalized recommendations
5. Frontend displays results with product links

For detailed documentation, see [AI_ASSISTANT.md](AI_ASSISTANT.md)

---

## 📸 Screenshots

### Home Page
- Hero section with call-to-action
- Search bar with real-time suggestions
- Product grid with pagination
- Category filters

### Product Detail Page
- Large product images
- Detailed descriptions
- Add to cart/wishlist buttons
- Customer reviews and ratings
- Similar products section

### Shopping Cart
- Cart items with images
- Quantity selectors
- Remove buttons
- Order summary with total
- Proceed to checkout button

### AI Shopping Assistant
- Floating circular button
- Expandable chat interface
- Quick action buttons
- Product recommendations with links
- Clear chat option

### Mobile View
- Hamburger menu
- Responsive layouts
- Touch-optimized buttons
- Full-width search bar

---

## 🎯 Key Accomplishments

✅ **Full-Stack Implementation** - Complete MERN stack with 3000+ lines of code  
✅ **AI Integration** - Google Gemini AI for intelligent recommendations  
✅ **Authentication System** - Secure JWT-based auth with password hashing  
✅ **Database Design** - 6 Mongoose models with relationships  
✅ **RESTful APIs** - 7 route modules with proper HTTP methods  
✅ **Responsive Design** - Mobile-first with 4 breakpoints  
✅ **Performance** - Optimized queries, caching, and lazy loading  
✅ **User Experience** - Smooth animations, loading states, error handling  
✅ **Email Integration** - Professional order confirmations  
✅ **Search Functionality** - Real-time suggestions and dedicated results page  

---

## 🧪 Testing

### Manual Testing Checklist

**Authentication:**
- [ ] Register new user
- [ ] Login with credentials
- [ ] JWT token stored in localStorage
- [ ] Protected routes redirect to login
- [ ] Logout clears token

**Shopping Flow:**
- [ ] Browse products
- [ ] Search with suggestions
- [ ] Filter by category
- [ ] View product details
- [ ] Add to cart (guest)
- [ ] Update quantities
- [ ] Remove items
- [ ] Checkout requires login
- [ ] Cart merges on login
- [ ] Order confirmation received

**AI Assistant:**
- [ ] Open chat interface
- [ ] Send query
- [ ] Receive recommendations
- [ ] Click product links
- [ ] Clear chat history

**Reviews & Wishlist:**
- [ ] Add product to wishlist
- [ ] View wishlist page
- [ ] Write product review
- [ ] View reviews on product page
- [ ] Mark review as helpful

---

## 🚀 Deployment

### Backend Deployment (Example: Heroku)
```bash
heroku create vibe-commerce-api
heroku config:set MONGODB_URI=your_mongodb_uri
heroku config:set JWT_SECRET=your_jwt_secret
heroku config:set GEMINI_API_KEY=your_gemini_key
git push heroku main
```

### Frontend Deployment (Example: Vercel)
```bash
npm run build
vercel --prod
```

Update frontend `api.js` with production backend URL.

---

## 🤝 Contributing

This is an internship assignment project. For educational purposes only.

---

## 📄 License

This project is created for internship screening purposes.

---

## 👨‍💻 Author

**Kathirvel S**  


---

## 📞 Support

For questions about this assignment, please contact the internship coordinator.

---

## 🙏 Acknowledgments

- Google Gemini AI for intelligent recommendations
- Unsplash for product images
- Resend for email service
- MongoDB for database solutions
- React team for the amazing framework

---

**Built with ❤️ for Vibe Commerce Internship Screening**


---

*Last Updated: November 6, 2025*
