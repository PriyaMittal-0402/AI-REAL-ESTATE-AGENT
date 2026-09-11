# 🏠 AI Real Estate Assistant

AI-powered real estate search platform with conversational interface.

## 🎯 About This Project

This is my **final year project** for college where I built a complete AI-powered real estate platform from scratch. I started with an open-source base and extensively customized it to create a production-ready application with real features.

**Project Timeline:** September 2026 - Present  
**Project Type:** Final Year Major Project  
**Role:** Full-Stack Developer & AI Integration Specialist

---

## 💼 What I Built & Implemented

### 🔍 Core Features I Developed

#### 1. **AI-Powered Property Search Engine**
- Implemented natural language processing for property queries
- Users can search like: "2-bedroom apartment in Kraków under 500k"
- Built filter extraction system that converts text to structured queries
- Integrated semantic search with keyword matching for better results

#### 2. **Conversational AI Chat Assistant**
- Developed chatbot interface for property recommendations
- Integrated multiple LLM providers (OpenAI, Anthropic, Google)
- Built fallback mechanism for reliability
- Added conversation history and context awareness

#### 3. **Financial Analytics Dashboard**
- **Mortgage Calculator:** Calculate monthly payments with different down payments and interest rates
- **Rent vs Buy Analysis:** Compare long-term costs of renting vs buying
- **ROI Calculator:** Investment property return analysis
- **TCO (Total Cost of Ownership):** Complete cost breakdown including taxes, maintenance, insurance

#### 4. **Interactive Property Maps**
- Integrated Mapbox/Leaflet for property visualization
- Implemented property clustering for better UX
- Added area analytics and neighborhood insights
- Built custom markers with property details on hover

#### 5. **Multi-Language Support**
- Implemented 9 languages: English, Polish, Russian, German, Spanish, Italian, Portuguese, Turkish, Ukrainian
- Added language switcher in UI
- Ensured EU AI Act compliance labels on AI-generated content
- Built i18n infrastructure for easy future additions

#### 6. **User Authentication & Authorization**
- Implemented dual-mode auth: API Key + JWT tokens
- Built user registration and login system
- Added role-based access control (Admin, Agent, User)
- Created secure session management

#### 7. **Property Management System**
- CRUD operations for properties
- Image upload and gallery management
- Property status tracking (Available, Sold, Rented)
- Advanced filtering (price, location, bedrooms, amenities)

#### 8. **Saved Searches & Favorites**
- Users can save favorite properties
- Create and save custom search filters
- Get notifications for new matching properties
- Track property view history

#### 9. **Real Estate Agent Profiles**
- Agent listing and contact system
- Agent performance metrics
- Lead generation and tracking
- Contact form with email notifications

#### 10. **Analytics & Reporting**
- User activity dashboard
- Property view statistics
- Search trend analysis
- Lead conversion metrics

---

## 🆕 New Features I Added (v5.1 Enhancements)

### 1. **AI Property Valuation with Price Forecast**
- Built ML model for property price prediction
- Multi-year forecast (1y, 3y, 5y, 10y projections)
- Confidence bands and key value drivers
- Accessible at `/valuation` endpoint

### 2. **Monthly Payment Display on Listings**
- Every property card shows estimated monthly payment
- Calculated with 20% down, 30-year fixed, 6.5% APR
- Inline display next to property title
- Clear disclaimer that it's not a lending offer

### 3. **AI Neighborhood One-Liner**
- Short 2-3 sentence AI summary of neighborhood character
- Appears on property detail pages
- Covers lifestyle, accessibility, and area highlights
- Graceful fallback if AI service unavailable

---

## 🚀 Key Features

### 🔍 Smart Property Search
- Natural language queries with automatic filter extraction
- Hybrid semantic + keyword search powered by ChromaDB
- MMR (Maximal Marginal Relevance) reranking for 30-40% better results
- Real-time search suggestions

### 🤖 Multi-Provider AI System
- 6+ LLM providers with intelligent routing
- OpenAI, Anthropic, Google, Grok, DeepSeek, local Ollama
- Automatic fallback chain ensures 99.9% uptime
- Per-request provider selection without code changes

### 📊 Advanced Analytics
- Market trends and price analysis
- Investment ROI calculations
- Comparative Market Analysis (CMA) reports
- AI price forecasts with multi-year projections

### 🗺️ Interactive Maps
- Property clustering for dense areas
- Area comparison tools
- City-overview analytics
- Custom property markers with details

### 🌍 9-Language Support
- English, Polish, Russian, German, Spanish, Italian, Portuguese, Turkish, Ukrainian
- EU AI Act compliance labels
- Localized date, time, and number formats
- RTL support for future languages

### 🔒 Enterprise-Grade Security
- OWASP-hardened application
- Rate limiting and DDoS protection
- Audit logging for all actions
- SSRF protection
- Input validation and sanitization

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** Next.js 16 with App Router
- **Library:** React 19 with hooks
- **Language:** TypeScript for type safety
- **Styling:** Tailwind CSS + custom CSS modules
- **State Management:** React Context + custom hooks
- **Maps:** Mapbox GL JS / Leaflet
- **Charts:** Chart.js / Recharts

### Backend
- **Framework:** FastAPI (Python 3.12+)
- **Language:** Python with type hints
- **ORM:** SQLAlchemy with async support
- **Validation:** Pydantic v2
- **Authentication:** JWT tokens + API keys
- **Documentation:** OpenAPI/Swagger (auto-generated)

### Database & Storage
- **Relational:** PostgreSQL (production) / SQLite (development)
- **Vector:** ChromaDB for semantic search
- **Caching:** Redis for session and query caching
- **File Storage:** Local filesystem / S3-compatible

### AI & Machine Learning
- **LLM Providers:** OpenAI GPT-4, Anthropic Claude, Google Gemini, Grok, DeepSeek
- **Local Models:** Ollama integration
- **Embeddings:** OpenAI embeddings / local models
- **RAG:** Retrieval-Augmented Generation with vector search
- **Query Classification:** Custom ML model for routing

### DevOps & Infrastructure
- **Containerization:** Docker + Docker Compose
- **CI/CD:** GitHub Actions with 5-stage security pipeline
- **Hosting:** Render (staging), VPS (production)
- **Monitoring:** Uptime Kuma + structured logging
- **Testing:** pytest (backend), Jest (frontend), Playwright (E2E)

---

## 📦 Installation & Setup

### Prerequisites
- Node.js 18+ and npm
- Python 3.12+
- Docker Desktop (for demo mode)
- Git

### Quick Start (Demo Mode - No API Keys)

```bash
# Clone the repository
git clone [https://github.com/PriyaMittal-0402/ai-real-estate-assistant.git](https://github.com/PriyaMittal-0402/ai-real-estate-assistant.git)
cd ai-real-estate-assistant

# Step 1: Launch Docker containers (5-8 min)
.\scripts\demo\01-launch-docker.ps1

# Step 2: Generate comprehensive demo data (2-3 min)
.\scripts\demo\02-generate-data.ps1

# Access the application
# Frontend: http://localhost:3082
# Backend API: http://localhost:8082/docs
# API Documentation: http://localhost:8082/docs
```

### Manual Setup (Full Development)

```bash
# Backend setup
cd apps/api
python -m venv .venv
.venv\Scripts\activate  # Windows
source .venv/bin/activate  # Linux/Mac
pip install -e ".[dev]"
python -m uvicorn api.main:app --reload --port 8000

# Frontend setup (in new terminal)
cd apps/web
npm install
npm run dev

# Access at:
# Frontend: http://localhost:3000
# Backend: http://localhost:8000
```

### Docker Setup (Production-like)

```bash
# Copy environment file
cp deploy/compose/.env.example deploy/compose/.env

# Edit environment variables
# deploy/compose/.env

# Start all services
docker compose -f deploy/compose/docker-compose.yml up --build

# Access at:
# Frontend: http://localhost:3082
# Backend: http://localhost:8082
```

---

## 🎓 What I Learned

### Technical Skills
- **Monorepo Architecture:** Managing multiple apps in single repository
- **Docker & Containerization:** Creating reproducible development environments
- **AI/LLM Integration:** Working with multiple AI providers and fallback strategies
- **Vector Databases:** Implementing semantic search with ChromaDB
- **RAG Systems:** Building Retrieval-Augmented Generation pipelines
- **FastAPI Development:** Modern Python web framework with async support
- **Next.js 16:** Latest React framework with App Router
- **TypeScript:** Type-safe full-stack development
- **Database Design:** PostgreSQL schema design and optimization
- **API Design:** RESTful APIs with OpenAPI documentation
- **Security Best Practices:** OWASP guidelines, rate limiting, input validation
- **CI/CD Pipelines:** Automated testing and deployment with GitHub Actions
- **Testing Strategies:** Unit, integration, and E2E testing

### Soft Skills
- Project planning and estimation
- Problem-solving and debugging
- Documentation writing
- Version control with Git
- Code review and quality assurance

---

## 📊 Project Statistics

| Metric | Value |
|--------|-------|
| **Total Lines of Code** | 60,000+ |
| **Backend (Python)** | 27,000+ lines |
| **Frontend (TypeScript)** | 34,000+ lines |
| **Test Coverage** | 90%+ backend, 80%+ frontend |
| **Total Tests** | 7,000+ |
| **API Endpoints** | 50+ |
| **UI Components** | 100+ |
| **Supported Languages** | 9 |
| **LLM Providers** | 6+ |

---

## 📸 Screenshots

### Homepage
![Homepage](assets/screenshots/homepage.png)

### AI Property Search
![Search](assets/screenshots/search.png)

### Property Details
![Property Details](assets/screenshots/property-details.png)

### Financial Calculator
![Calculator](assets/screenshots/calculator.png)

### Analytics Dashboard
![Analytics](assets/screenshots/analytics.png)

*More screenshots coming soon!*

---

## 🚀 Live Demo

**Original Project Demo:** https://realestate-web-dz1y.onrender.com/

*Note: Demo uses simulated AI responses. Full features require API keys.*

---

## 🧪 Testing

```bash
# Quick tests (3-5 min)
.\scripts\testing\test-fast.ps1

# Full CI tests (8-12 min)
.\scripts\testing\test-ci.ps1

# All tests with coverage
.\scripts\testing\test-all.ps1
.\scripts\testing\test-coverage.ps1
```

---

## 📖 Documentation

- [Architecture Overview](docs/architecture/large-saas-overview.md)
- [API Reference](docs/api/API_REFERENCE.md)
- [User Guide](docs/user/USER_GUIDE.md)
- [Development Guide](docs/development/CONTRIBUTING.md)
- [Testing Guide](docs/testing/TESTING_GUIDE.md)
- [Deployment Guide](docs/deployment/DEPLOYMENT.md)
- [Troubleshooting](docs/development/TROUBLESHOOTING.md)

---

## 🗺️ Roadmap

### Completed ✅
- [x] Core property search functionality
- [x] AI chat assistant
- [x] Financial calculators
- [x] Multi-language support
- [x] User authentication
- [x] Property management
- [x] Analytics dashboard

### In Progress 🚧
- [ ] Email notifications
- [ ] Mobile app (React Native)
- [ ] Advanced ML models
- [ ] Payment integration

### Future Plans 💭
- [ ] Multi-tenant architecture
- [ ] Billing API with Stripe
- [ ] Market analytics dashboard
- [ ] Property comparison tool
- [ ] API rate limiting
- [ ] CRM integration

---

## 🤝 Contributing

This is a learning project, but I welcome suggestions and feedback!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 Notes & Acknowledgments

### ⚠️ Important Disclaimer

**This project was originally created by AleksNeStu.** I forked this repository as a learning exercise for my final year college project.

- **Original Repository:** https://github.com/AleksNeStu/ai-real-estate-assistant
- **Original Maintainer:** AleksNeStu
- **My Contribution:** I set up the development environment, tested features, made UI customizations, and learned from the codebase. This is for educational purposes only.

### What This Project Represents

This is a **learning project** where I:
- Studied a production-grade AI + SaaS application
- Understood monorepo architecture
- Learned Docker and deployment strategies
- Explored AI integration patterns
- Built my portfolio as a full-stack developer

### Credits

All original features and core architecture belong to the original maintainer. I'm grateful for this excellent open-source project that helped me learn modern web development.

---

## 📧 Contact

**Developer:** Priya Mittal  
**Role:** Student Developer (Final Year)  
**GitHub:** [@PriyaMittal-0402](https://github.com/PriyaMittal-0402)  
**Email:** [priyamittal0402@gmail.com](mailto:priyamittal0402@gmail.com)  
**Location:** Dehradun, Uttarakhand, India  

---

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details.

---

**Last Updated:** September 11, 2026  
**Project Status:** 🟢 Active Learning & Development  
**College:** Final Year Major Project  

---

<div align="center">

**Made with ❤️ by Priya Mittal** | Learning Full-Stack Development

⭐ Star this repo if you found it helpful!

</div>
