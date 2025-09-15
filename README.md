# 🍽️ Grub Guru Bot

An AI-powered restaurant recommendation and ordering system built for the OpenAI x NxtWave Hackathon. Grub Guru Bot uses artificial intelligence to provide personalized restaurant recommendations, menu suggestions, and seamless ordering experiences.

## ✨ Features

### 🤖 AI-Powered Recommendations
- **Smart Restaurant Discovery**: Get personalized restaurant recommendations based on your preferences
- **Intelligent Menu Suggestions**: AI analyzes your dietary preferences and suggests the perfect dishes
- **Natural Language Processing**: Chat with the bot using natural language to express your cravings

### 🍕 Core Functionality
- **Multi-Step Ordering Flow**: From preferences to restaurant selection to menu ordering
- **Famous Restaurants**: Browse curated list of top-rated restaurants
- **Special Dishes**: Discover trending, award-winning, and chef's special dishes
- **Advanced Search**: Find restaurants and dishes with powerful filtering options
- **Favorites System**: Save your favorite restaurants and dishes for quick access

### 🛠️ Technical Features
- **Real-time Database**: Powered by Supabase for scalable data management
- **AI Integration**: Hugging Face API for natural language processing
- **Responsive Design**: Beautiful, mobile-first UI built with React and TypeScript
- **RESTful API**: Clean backend architecture with Express.js
- **Modern Stack**: Latest technologies for optimal performance

## 🏗️ Architecture

```
grub-guru-bot/
├── src/                    # Frontend (React + TypeScript)
│   ├── components/         # Reusable UI components
│   ├── pages/             # Main application pages
│   └── lib/               # API utilities and types
├── server/                # Backend (Node.js + Express)
│   └── src/
│       ├── routes.js      # API endpoints
│       ├── supabaseClient.js  # Database connection
│       └── hf.js          # Hugging Face AI integration
├── supabase/              # Database schema and seed data
└── docs/                  # Documentation
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- Supabase account
- Hugging Face API key (optional)

### 1. Clone the Repository
```bash
git clone <repository-url>
cd grub-guru-bot
```

### 2. Install Dependencies

**Frontend:**
```bash
npm install
```

**Backend:**
```bash
cd server
npm install
cd ..
```

### 3. Set Up Supabase Database

1. Create a new project at [supabase.com](https://supabase.com)
2. Get your project URL and anon key from Settings → API
3. Run the database schema:
   ```sql
   -- Copy and paste contents of supabase/schema.sql in Supabase SQL Editor
   ```
4. Seed the database:
   ```sql
   -- Copy and paste contents of supabase/seed_data.sql in Supabase SQL Editor
   ```

### 4. Configure Environment Variables

Create `server/.env`:
```env
PORT=4000
SUPABASE_URL=https://your-project-id.supabase.co
SUPABASE_ANON_KEY=eyJ...your-anon-key-here
HUGGINGFACE_API_KEY=your-hf-api-key-here
```

### 5. Start the Application

**Start the backend server:**
```bash
cd server
npm run dev
```

**Start the frontend (in a new terminal):**
```bash
npm run dev
```

The application will be available at:
- Frontend: `http://localhost:5173`
- Backend API: `http://localhost:4000`

## 📱 How to Use

### 1. AI Restaurant Experience
- Click "Get Started" to begin the AI-powered recommendation flow
- Chat with the bot to express your preferences (budget, cuisine, ambience, dietary restrictions)
- Get personalized restaurant recommendations
- Select a restaurant and receive AI-suggested menu items
- Complete your order with a confirmation summary

### 2. Explore Famous Restaurants
- Browse curated list of top-rated restaurants
- Filter by cuisine type and location
- View detailed information including ratings and specialties

### 3. Discover Special Dishes
- Explore trending dishes across the platform
- Find award-winning and chef's special items
- Filter by cuisine type and dietary preferences

### 4. Advanced Search
- Use the search functionality to find specific restaurants or dishes
- Apply multiple filters for precise results
- Save favorites for quick access

## 🔧 API Endpoints

### Restaurant Recommendations
```http
POST /api/restaurants/recommend
Content-Type: application/json

{
  "budget": "medium",
  "cuisine": "italian",
  "ambience": "romantic",
  "veg": true
}
```

### Menu Suggestions
```http
POST /api/menu/suggest
Content-Type: application/json

{
  "restaurantId": "restaurant-uuid",
  "preferences": {
    "veg": true
  }
}
```

### Famous Restaurants
```http
GET /api/restaurants/famous?locality=mumbai&cuisine=indian
```

### Special Dishes
```http
GET /api/dishes/special?filter=trending&cuisine=chinese
```

### Create Order
```http
POST /api/orders
Content-Type: application/json

{
  "user_id": "user123",
  "restaurant_id": "restaurant-uuid",
  "dish_ids": ["dish-uuid-1", "dish-uuid-2"],
  "quantities": [2, 1],
  "total_amount": 45.99,
  "special_instructions": "Extra spicy"
}
```

## 🗄️ Database Schema

The application uses the following main tables:

- **restaurants**: Restaurant information, ratings, and metadata
- **menus**: Dish details, pricing, and dietary information
- **orders**: Order tracking and management
- **reservations**: Table booking system
- **user_preferences**: AI recommendation preferences

## 🎨 Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development and building
- **Tailwind CSS** for styling
- **Lucide React** for icons
- **Axios** for API calls

### Backend
- **Node.js** with Express.js
- **Supabase** for database and real-time features
- **Hugging Face API** for AI capabilities
- **CORS** for cross-origin requests

### Database
- **PostgreSQL** (via Supabase)
- **Real-time subscriptions**
- **Row Level Security (RLS)**

## 🤖 AI Integration

The application leverages Hugging Face's AI models for:
- **Text Generation**: Creating personalized explanations for menu recommendations
- **Natural Language Processing**: Understanding user preferences from chat input
- **Embeddings**: For semantic search and recommendation matching

## 🚀 Deployment

### Frontend (Vercel/Netlify)
1. Build the project: `npm run build`
2. Deploy the `dist` folder to your hosting platform
3. Set environment variables for API endpoints

### Backend (Railway/Heroku)
1. Set up environment variables in your hosting platform
2. Deploy the `server` folder
3. Ensure the database connection is properly configured

### Database (Supabase)
- The database is already hosted on Supabase
- Configure RLS policies for production security
- Set up proper API keys and access controls

## 🧪 Testing

Test the API endpoints:
```bash
# Health check
curl http://localhost:4000/health

# Get famous restaurants
curl http://localhost:4000/api/restaurants/famous

# Test AI generation
curl -X POST http://localhost:4000/api/generate \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Recommend a good Italian restaurant"}'
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏆 Hackathon Details

Built for the **OpenAI x NxtWave Hackathon** with the following focus areas:
- **AI Integration**: Leveraging Hugging Face models for intelligent recommendations
- **User Experience**: Seamless, conversational interface for restaurant discovery
- **Scalability**: Modern architecture ready for production deployment
- **Innovation**: Combining AI with practical food ordering use case

## 📞 Support

For support, email your-email@example.com or create an issue in the repository.

---

**Made with ❤️ for the OpenAI x NxtWave Hackathon**
