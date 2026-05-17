# 🚀 QUICK SETUP GUIDE - ShopEase

## 📦 What You Have

A complete, production-ready e-commerce platform with:
- ✅ Beautiful React frontend with Tailwind CSS
- ✅ RESTful Node.js/Express backend
- ✅ MongoDB database integration
- ✅ JWT + Google OAuth authentication
- ✅ Email OTP verification
- ✅ Complete admin panel
- ✅ Seller management system
- ✅ Negotiation/Bargain system
- ✅ Smart Spending Report
- ✅ 12 pre-seeded products
- ✅ Responsive design (Mobile + Desktop)
- ✅ Smooth animations

---

## ⚡ SETUP STEPS

### Step 1: Install Dependencies

**Backend:**
```bash
cd backend
npm install
```

**Frontend:**
```bash
cd frontend
npm install
```

### Step 2: Setup Environment Variables

**`backend/.env`:**
```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=any_random_secret_key
JWT_EXPIRE=30d
PORT=5000
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
CLIENT_URL=http://localhost:5173
BACKEND_URL=http://localhost:5000
EMAIL_USER=your_gmail@gmail.com
EMAIL_PASS=your_gmail_app_password
SESSION_SECRET=any_random_string
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_secret
```

**`frontend/.env`:**
```
VITE_API_URL=http://localhost:5000
```

### Step 3: Seed Database

```bash
cd backend
node utils/seedProducts.js
```

This creates:
- **Admin**: admin@shopease.com / admin123
- **12 sample products** with seller field

### Step 4: Run the Application

**Terminal 1 (Backend):**
```bash
cd backend
npm run dev
```
Runs on: http://localhost:5000

**Terminal 2 (Frontend):**
```bash
cd frontend
npm run dev
```
Runs on: http://localhost:5173

---

## 🔑 Login Credentials

| Role | Email | Password |
|------|-------|----------|
| Admin | admin@shopease.com | admin123 |
| User | Register from signup page | - |

---

## 🎯 TESTING CHECKLIST

### User Flow:
- [ ] Register with Email OTP verification
- [ ] Login with Google OAuth
- [ ] Browse & search products
- [ ] Filter by category/price
- [ ] View product details
- [ ] Add to cart → Go to Cart button
- [ ] Place order
- [ ] View order history
- [ ] Make negotiation offer
- [ ] View spending report
- [ ] Forgot password with OTP

### Seller Flow:
- [ ] Apply to become seller (Admin approval needed)
- [ ] Add product (Admin approval needed)
- [ ] View pending approval badge on dashboard
- [ ] Manage own products
- [ ] View negotiation badge in navbar
- [ ] Accept/Reject/Counter negotiations
- [ ] View & manage own orders

### Admin Flow:
- [ ] View dashboard stats
- [ ] Approve/Reject seller requests (AdminUsers page)
- [ ] Approve/Reject products (ManageProducts page)
- [ ] View products grouped by seller
- [ ] Manage all orders
- [ ] View all negotiations
- [ ] Remove seller access
- [ ] Delete users

---

## 🌟 UNIQUE FEATURES

### 1. 🤝 Bargain/Negotiate Price
- Users can send price offers to sellers
- Sellers can Accept, Reject, or Counter offer
- Maximum 3 offers per product
- Real-time badge notification for sellers

### 2. 📊 Smart Spending Report
- Monthly spending chart
- Category-wise spending breakdown
- Visual charts with Recharts

### 3. 🔐 Seller Approval System
- Users apply to become sellers
- Admin approves/rejects requests
- 3 rejection limit — permanently blocked

### 4. ✅ Product Approval System
- Sellers add products — pending by default
- Admin approves before product goes live
- Badge notification for admin

### 5. 📧 Email OTP Verification
- Registration requires email OTP
- Forgot password via OTP
- 10 minute OTP expiry

### 6. 🌐 Google OAuth
- One-click Google login
- Auto account creation on first login

---

## 🐛 TROUBLESHOOTING

**Problem**: Backend won't start
**Solution**: Check `.env` file — all variables filled?

**Problem**: OTP not received
**Solution**: Check Gmail App Password in `.env` — use App Password not Gmail password

**Problem**: Google login not working
**Solution**: Check `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` in `.env`

**Problem**: Products not showing
**Solution**: Run `node utils/seedProducts.js` in backend

**Problem**: CORS error
**Solution**: Check `CLIENT_URL` in backend `.env` matches frontend URL

---

## 📚 API ENDPOINTS QUICK REFERENCE

### Auth
- `POST /api/auth/send-register-otp` - Send OTP
- `POST /api/auth/verify-register-otp` - Verify & Register
- `POST /api/auth/login` - Login
- `GET /api/auth/google` - Google OAuth
- `POST /api/auth/forgot-password` - Send reset OTP
- `POST /api/auth/reset-password` - Reset password

### Products
- `GET /api/products` - All active products
- `GET /api/products/featured` - Featured products
- `GET /api/products/admin/all` - All products (Admin)
- `POST /api/products` - Create (Admin)

### Orders
- `POST /api/orders` - Place order
- `GET /api/orders/myorders` - My orders
- `GET /api/orders/seller-orders` - Seller orders
- `PUT /api/orders/:id/status` - Update status

### Negotiations
- `POST /api/negotiations` - Make offer
- `GET /api/negotiations/my` - My offers
- `GET /api/negotiations/seller` - Seller offers
- `PUT /api/negotiations/:id` - Respond to offer

### Admin
- `GET /api/admin/stats` - Dashboard stats
- `GET /api/admin/users` - All users
- `PUT /api/admin/users/:id/approve-seller` - Approve seller
- `PUT /api/admin/products/:id/approve` - Approve product

---

## 🎓 FOR VIVA/PRESENTATION

**Key Points to Mention:**
1. **Tech Stack**: MERN (MongoDB, Express, React, Node.js)
2. **Authentication**: JWT + Google OAuth + Email OTP
3. **Unique Features**: Bargain system, Spending Report, Seller Approval, Product Approval
4. **Security**: Bcrypt hashing, Role-based access, OTP verification
5. **UI/UX**: Responsive, animations, real-time badges
6. **State Management**: React Context API

**Demo Flow:**
1. Show homepage with products
2. Register with OTP verification
3. Browse & search products
4. Add to cart & checkout
5. Make negotiation offer
6. Login as seller — show badges
7. Login as admin — approve products/sellers
8. Show spending report

---

