# 💄 Avon Cosmetica

A luxurious e-commerce experience for Avon beauty products, inspired by high-end retailers like Charlotte Tilbury and Sephora.

![Avon Cosmetica](https://images.unsplash.com/photo-1596462502278-27bfdc403348?w=1200&h=400&fit=crop)

## ✨ Features

### 🛍️ Shopping Experience
- **Product Catalog**: 12+ curated Avon best-sellers from 2025
- **Smart Search**: Real-time product search functionality
- **Category Filtering**: Browse by Skincare, Makeup, Fragrance, and Body Care
- **Product Cards**: Premium cards with ratings, reviews, and wishlist integration
- **Shopping Cart**: Slide-out cart with promo code support (try `WELCOME20` for 20% off)
- **Wishlist**: Save your favorite products for later

### 🎨 Design System
- **Color Palette**: Elegant rose/pink with burgundy accents and gold highlights
- **Typography**: Playfair Display for headings, modern sans-serif for body text
- **Animations**: Subtle hover effects and smooth transitions
- **Responsive**: Fully mobile-friendly design
- **Premium Feel**: Soft gradients and sophisticated layouts

### 🔔 User Experience
- **Notifications**: Toast notifications for cart actions and wishlist updates
- **Rating System**: Star ratings and review counts on all products
- **Promo Codes**: Apply discount codes at checkout
- **Empty States**: Beautiful illustrations for empty cart/wishlist states

### 💳 Payment Processing
- **PayChangu Integration**: Secure payment processing for Malawi
- **Multiple Payment Methods**: Mobile money (Airtel Money, TNM Mpamba), bank cards
- **Local Currency**: MWK (Malawian Kwacha) support
- **Secure Checkout**: PCI-compliant payment processing
- **Payment Confirmation**: Real-time payment status updates

## 🚀 Getting Started

### Prerequisites
- Node.js 16+ and npm/yarn
- Modern web browser

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/avon-cosmetica.git

# Navigate to project directory
cd avon-cosmetica

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Add your PayChangu API keys to .env

# Start development server
npm run dev
```

### Environment Variables

Create a `.env` file in the root directory:

```env
VITE_PAYCHANGU_SECRET_KEY=your_secret_key_here
VITE_PAYCHANGU_PUBLIC_KEY=your_public_key_here
VITE_PAYCHANGU_CALLBACK_URL=https://yourdomain.com/payment-callback
```

Get your API keys from [PayChangu Dashboard](https://dashboard.paychangu.com)

### Build for Production

```bash
# Create optimized production build
npm run build

# Preview production build
npm run preview
```

## 🛠️ Tech Stack

- **React** - UI library
- **TypeScript** - Type safety
- **Tailwind CSS** - Utility-first styling
- **Lucide React** - Beautiful icons
- **Vite** - Fast build tool
- **PayChangu** - Payment processing for Malawi

## 📦 Project Structure

```
avon-cosmetica/
├── src/
│   ├── components/
│   │   ├── Header.tsx          # Navigation and search
│   │   ├── Hero.tsx            # Hero banner section
│   │   ├── ProductCard.tsx     # Product display cards
│   │   ├── Cart.tsx            # Shopping cart sidebar
│   │   ├── Checkout.tsx        # Checkout component
│   │   ├── PaymentForm.tsx     # PayChangu integration
│   │   └── Notification.tsx    # Toast notifications
│   ├── data/
│   │   └── products.ts         # Product catalog data
│   ├── services/
│   │   └── paychangu.ts        # PayChangu API service
│   ├── types/
│   │   └── index.ts            # TypeScript interfaces
│   ├── App.tsx                 # Main application
│   └── main.tsx                # Application entry
├── public/                     # Static assets
├── .env.example                # Environment variables template
└── package.json
```

## 🎯 Product Categories

1. **Skincare** - Serums, moisturizers, and treatments
2. **Makeup** - Lipsticks, eyeliners, and mascaras
3. **Fragrance** - Signature Avon scents
4. **Body Care** - Body lotions and oils

## 💳 Promo Codes

Try these codes at checkout:
- `WELCOME20` - 20% off your order
- `BEAUTY15` - 15% off
- `GLOW10` - 10% off

## 💰 Payment Integration

### PayChangu Setup

1. **Create PayChangu Account**
   - Sign up at [paychangu.com](https://paychangu.com)
   - Complete business verification
   - Get your API keys from the dashboard

2. **Configure Payment Methods**
   - Airtel Money
   - TNM Mpamba
   - Visa/Mastercard

3. **Test Mode**
   - Use test credentials for development
   - Test cards and mobile numbers available in PayChangu docs

4. **Webhook Setup**
   - Configure webhook URL in PayChangu dashboard
   - Handle payment notifications at `/api/paychangu-webhook`

### Payment Flow

```typescript
// 1. Customer clicks "Checkout"
// 2. Payment request sent to PayChangu
const paymentData = {
  amount: totalAmount,
  currency: 'MWK',
  email: customerEmail,
  first_name: firstName,
  last_name: lastName,
  callback_url: process.env.VITE_PAYCHANGU_CALLBACK_URL,
  return_url: 'https://yourdomain.com/order-confirmation',
  tx_ref: generateTransactionRef(),
  customization: {
    title: 'Avon Cosmetica',
    description: 'Beauty Products Purchase'
  }
};

// 3. Customer redirected to PayChangu payment page
// 4. Payment processed via mobile money or card
// 5. Customer redirected back with payment status
// 6. Order confirmed and email sent
```

### Supported Currencies
- **MWK** (Malawian Kwacha) - Primary
- **USD** (US Dollar) - Coming soon

## 🎨 Customization

### Colors
The color scheme can be customized in your Tailwind config:
```javascript
colors: {
  rose: { /* pink shades */ },
  burgundy: { /* burgundy shades */ },
  gold: { /* gold accents */ }
}
```

### Adding Products
Add new products to `src/data/products.ts`:
```typescript
{
  id: 'unique-id',
  name: 'Product Name',
  category: 'makeup',
  price: 29.99,
  image: 'image-url',
  rating: 4.5,
  reviews: 123,
  description: 'Product description'
}
```

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Design inspiration from Charlotte Tilbury and Sephora
- Product images from Unsplash
- Icons from Lucide React

## 📧 Contact

For questions or support, please open an issue on GitHub.

---

**Made with 💖 for Avon beauty lovers**
