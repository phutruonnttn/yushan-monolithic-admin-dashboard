# Yushan Monolithic Admin Dashboard

> 🛠️ **Admin Dashboard for Yushan Platform (Phase 1 - Monolithic)** - Administrative dashboard for the gamified web novel reading platform.

## 📋 Overview

This is the admin dashboard for the monolithic version of Yushan Platform, which is Phase 1 of the project. This dashboard provides comprehensive administrative tools to manage users, content, interactions, and analytics.

## 🚀 Tech Stack

- **Framework**: React 18.3.1
- **Build Tool**: Create React App
- **Language**: JavaScript
- **UI Library**: Ant Design 5.27.4
- **State Management**: Zustand 4.5.5 (optional)
- **Routing**: React Router DOM 6.26.2
- **HTTP Client**: Axios 1.12.2
- **Charts**: Recharts 2.12.7
- **Testing**: Jest, React Testing Library

## ✨ Key Features

### 🔐 Authentication
- Admin-only login
- JWT token authentication
- Automatic token refresh (every 15 minutes)
- Session management

### 👥 User Management
- User list (pagination, filtering)
- View user details
- Update user status (active/ban)
- Promote to Admin
- Author management
- User statistics

### 📚 Content Management
- Novel management (CRUD)
- Chapter management (CRUD)
- Category management
- Content review and approval
- Hide/show content
- Cover image upload

### 💬 Interaction Management
- Comment management
- Review management
- Report handling
- Content moderation

### 📊 Analytics & Reports
- Dashboard with overview metrics
- User statistics (DAU, WAU, MAU)
- Content statistics
- Rankings
- Charts and visualizations

### 💰 Gamification Management
- Yuan transaction management
- Gamification statistics
- View user achievements

### 📖 Library Management
- View user libraries
- Reading history management

## 🏗️ Project Structure

```
src/
├── components/
│   └── admin/
│       ├── common/         # Common components (Header, Sidebar, Layout)
│       ├── charts/         # Chart components
│       ├── tables/         # Data table components
│       └── modals/         # Modal components
├── pages/
│   └── admin/
│       ├── dashboard/      # Main dashboard
│       ├── users/          # User management
│       ├── novels/         # Novel management
│       ├── chapters/       # Chapter management
│       ├── categories/     # Category management
│       ├── comments/       # Comment management
│       ├── reviews/        # Review management
│       ├── reports/        # Report handling
│       ├── library/        # Library management
│       ├── rankings/       # Rankings
│       ├── yuan/           # Yuan management
│       ├── settings/       # Settings
│       └── profile/        # Admin profile
├── services/
│   └── admin/
│       ├── api.js          # Axios instance
│       ├── authservice.js  # Authentication
│       ├── userservice.js  # User management
│       ├── novelservice.js # Novel management
│       ├── chapterservice.js
│       ├── commentservice.js
│       ├── reviewservice.js
│       ├── reportservice.js
│       ├── analyticsservice.js
│       ├── rankingservice.js
│       └── dashboardservice.js
├── contexts/
│   └── admin/
│       ├── adminauthcontext.jsx
│       └── ...
├── hooks/
│   └── admin/
│       ├── useAdminAuth.js
│       ├── useDashboardData.js
│       ├── useDataTable.js
│       └── ...
└── styles/
    └── admin/
        ├── layout.css
        ├── sidebar.css
        └── ...
```

## 🚦 Getting Started

### Prerequisites

- Node.js 18.x or higher
- npm or yarn
- Yushan Monolithic Backend running (default: `http://localhost:8080`)

### Installation

1. Clone repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create `.env` file (if needed):
   ```env
   REACT_APP_API_BASE_URL=http://localhost:8080/api
   ```
4. Start development server:
   ```bash
   npm start
   ```

### Environment Variables

- `REACT_APP_API_BASE_URL`: Base URL for Yushan API (default: `http://localhost:8080/api`)

## 📜 Available Scripts

### `npm start`

Runs the app in development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

### `npm test`

Launches the test runner in interactive watch mode.

### `npm run build`

Builds the app for production to the `build` folder.

### `npm run deploy`

Deploy to GitHub Pages.

## 🔐 Authentication

Admin dashboard integrates with Yushan authentication API:

- **Login**: `POST /api/auth/login` - Requires Admin privileges
- **Logout**: `POST /api/auth/logout` - Clear session
- **Refresh**: `POST /api/auth/refresh` - Automatic token refresh every 15 minutes

### Demo Credentials

- Email: `admin@yushan.com`
- Password: `admin`

## 🎨 UI Components

### Charts
- StatCard - Display statistics
- LineChart - Line chart
- AreaChart - Area chart
- BarChart - Bar chart
- PieChart - Pie chart

### Tables
- DataTable - Data table with pagination, filtering, sorting
- Export functionality
- Bulk actions

### Modals
- UserModal - Create/edit user
- NovelModal - Create/edit novel
- CommentModal - View/edit comment
- ReportModal - Handle report

## 📊 Dashboard Features

- **Overview Metrics**: Total users, novels, comments, etc.
- **User Statistics**: DAU, WAU, MAU
- **Content Statistics**: New novels, new chapters, etc.
- **Charts**: Visualizations for important metrics
- **Recent Activity**: Recent activities

## 🔗 API Integration

Dashboard connects to the following endpoints:

- **Auth**: `/api/auth/login`, `/api/auth/logout`, `/api/auth/refresh`
- **Users**: `/api/admin/users`, `/api/admin/users/{id}`, `/api/admin/promote-to-admin`
- **Novels**: `/api/admin/novels`, `/api/novels/{id}`
- **Chapters**: `/api/chapters`, `/api/chapters/{id}`
- **Comments**: `/api/comments`, `/api/comments/{id}`
- **Reviews**: `/api/reviews`, `/api/reviews/{id}`
- **Reports**: `/api/reports`
- **Analytics**: `/api/analytics/**`
- **Rankings**: `/api/rankings/**`

## 🧪 Testing

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:ci
```

## 🛠️ Built With

- [React](https://reactjs.org/) - Frontend framework
- [Create React App](https://create-react-app.dev/) - Build toolchain
- [Ant Design](https://ant.design/) - UI component library
- [React Router](https://reactrouter.com/) - Client-side routing
- [Axios](https://axios-http.com/) - HTTP client
- [Recharts](https://recharts.org/) - Charts library
- [Zustand](https://zustand-demo.pmnd.rs/) - State management (optional)
- [React Testing Library](https://testing-library.com/react) - Testing utilities

## 🔐 Security

- Admin-only access
- JWT token authentication
- Automatic token refresh
- Protected routes
- Session management

## 📱 Deployment

### Development

```bash
npm start
```

### Production Build

```bash
npm run build
# Deploy the 'build' folder to your hosting service
```

### GitHub Pages

```bash
npm run build
npm run deploy
```

## 🤝 Contributing

1. Fork repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📄 License

This project is part of the Yushan Platform ecosystem.

## 🔗 Links

- **Backend**: [yushan-monolithic-backend](https://github.com/phutruonnttn/yushan-monolithic-backend)
- **Frontend**: [yushan-monolithic-frontend](https://github.com/phutruonnttn/yushan-monolithic-frontend)
- **Platform Documentation**: [yushan-platform-docs](https://github.com/phutruonnttn/yushan-platform-docs) - Complete documentation for all phases
- **Phase 2 (Microservices)**: See [Phase 2 Architecture](https://github.com/phutruonnttn/yushan-platform-docs/blob/main/docs/phase2-microservices/PHASE2_MICROSERVICES_ARCHITECTURE.md)

---

**Yushan Monolithic Admin Dashboard** - Phase 1 of the administrative dashboard 🚀
