# Hostel Management System - Frontend

A modern, responsive React-based admin dashboard for hostel management.

## 🚀 Tech Stack

- **React** (v18.2.0) - UI library
- **React Router DOM** (v6.20.0) - Client-side routing
- **Axios** - HTTP client
- **React Hook Form** - Form management
- **React Icons** - Icon library
- **Chart.js** - Data visualization
- **Vite** - Build tool
- **CSS3** - Styling with custom CSS

## 📋 Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Backend API running on http://localhost:5000

## 🔧 Installation

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```

   The app will open at `http://localhost:3000`

4. **Build for production**
   ```bash
   npm run build
   ```

   The build output will be in the `dist/` directory.

## 📁 Project Structure

```
frontend/
├── src/
│   ├── components/
│   │   ├── Sidebar.jsx
│   │   ├── Sidebar.css
│   │   ├── Navbar.jsx
│   │   ├── Navbar.css
│   │   ├── Modal.jsx
│   │   ├── Modal.css
│   │   ├── DashboardCard.jsx
│   │   ├── DashboardCard.css
│   │   └── ProtectedRoute.jsx
│   ├── context/
│   │   └── AuthContext.jsx
│   ├── pages/
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   ├── Auth.css
│   │   ├── Dashboard.jsx
│   │   ├── Dashboard.css
│   │   ├── Students.jsx
│   │   ├── Rooms.jsx
│   │   ├── Payments.jsx
│   │   ├── Complains.jsx
│   │   ├── Staff.jsx
│   │   ├── Profile.jsx
│   │   ├── Profile.css
│   │   └── CRUD.css
│   ├── services/
│   │   └── api.js
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── index.html
├── vite.config.js
├── package.json
├── .gitignore
└── README.md
```

## 🎨 Pages & Features

### Authentication Pages
- **Login** - Admin login with email and password
- **Register** - New admin registration

### Dashboard
- Overview statistics cards
- Total students, rooms, payments, staff
- Available and fillup rooms
- Pending and solved complaints
- Quick access to all modules

### Students Management
- View all students with pagination
- Search by ID, name, or phone
- Add new student
- Edit student information
- Delete student
- Gender classification

### Rooms Management
- List all rooms with status
- Search functionality
- Add/Edit room details (type, capacity, occupied)
- Automatic status update (Available/Fillup)
- Delete rooms

### Payments Management
- Track all payments
- Filter by status (Paid/Pending)
- Search students
- Add/Edit payment records
- Date tracking
- Amount management

### Complains Management
- Log and track complaints
- Filter by status (Pending/Solved)
- Search by student or issue
- Add/Edit complaint details
- Mark as solved

### Staff Management
- Manage staff members
- Filter by shift (Day/Night)
- Salary tracking
- Position management
- Search functionality

### Profile Management
- View admin profile
- Edit personal information
- Change password
- Email and phone management

## 🔐 Authentication

The frontend uses JWT-based authentication:

1. **Login** - Credentials sent to backend
2. **Token Storage** - JWT token stored in localStorage
3. **API Requests** - Token automatically attached to all API requests
4. **Session Management** - Logout clears token and user data

## 📡 API Integration

All API calls are made through `services/api.js`:

```javascript
import { studentAPI, roomAPI, paymentAPI, complainAPI, staffAPI } from './services/api';

// Example: Get all students
const response = await studentAPI.getAll({ search: 'John', page: 1, limit: 10 });
```

## 🎯 Components

### Sidebar
- Navigation menu
- Active route highlighting
- Responsive mobile menu
- Logout functionality
- Animated menu toggle

### Navbar
- Search bar
- Notification bell
- Admin profile display
- Sticky positioning

### DashboardCard
- Statistics display
- Color-coded categories
- Icon integration
- Hover animations

### Modal
- Reusable form modal
- Smooth animations
- Close functionality
- Form validation

### ProtectedRoute
- Route authentication
- Automatic redirect to login
- Loading state handling

## 🎨 Styling

The project uses:
- **Custom CSS** for all components
- **CSS Variables** for consistent theming
- **Responsive Design** with mobile-first approach
- **Flexbox** for layouts
- **Grid** for complex layouts

Color Theme:
- Primary: #2563eb (Blue)
- Secondary: #1e40af (Dark Blue)
- Success: #10b981 (Green)
- Warning: #f59e0b (Orange)
- Danger: #ef4444 (Red)

## 📱 Responsive Design

The dashboard is fully responsive:
- **Desktop**: Full sidebar navigation, multi-column layouts
- **Tablet**: Collapsible sidebar, adjusted spacing
- **Mobile**: Hamburger menu, single-column layouts, optimized touch targets

## 🔄 State Management

Uses React Context API for:
- Authentication state
- User information
- Token management

Component-level state with `useState` for:
- Form data
- Loading states
- Modal visibility
- Pagination

## 🚀 Deployment

### Vercel
```bash
npm run build
# Deploy the dist/ folder to Vercel
```

### Other Platforms
```bash
npm run build
# Deploy dist/ folder to your hosting service
```

### Environment Variables
Create `.env.local` file:
```
REACT_APP_API_URL=http://localhost:5000/api
```

## 🐛 Debugging

Enable debug logging in the browser console. The app logs:
- API requests/responses
- Authentication state changes
- Component lifecycle events

## ⚡ Performance Optimization

- Code splitting with React Router
- Lazy loading of pages
- Optimized re-renders
- Image optimization
- CSS minification in production

## 🔐 Security

- JWT token-based authentication
- Secure API endpoint calls
- Protected routes with authentication check
- Automatic logout on token expiration
- XSS protection through React's built-in escaping

## 📝 Common Tasks

### Adding a New Page
1. Create page file in `src/pages/`
2. Create corresponding CSS file
3. Add route in `App.jsx`
4. Add navigation link in `Sidebar.jsx`

### Adding a New API Endpoint
1. Add method in `services/api.js`
2. Use in component with appropriate error handling

### Styling a Component
1. Create `.css` file next to component
2. Import in component file
3. Use BEM or component naming conventions

## 🆘 Troubleshooting

### API Connection Issues
- Ensure backend is running on port 5000
- Check CORS configuration in backend
- Verify JWT token is valid

### Module Not Found
- Run `npm install`
- Clear node_modules: `rm -rf node_modules && npm install`

### Build Issues
- Clear Vite cache: `rm -rf dist/`
- Update dependencies: `npm update`

## 📄 License

This project is licensed under the ISC License.

## 🤝 Contributing

Please ensure code follows the existing patterns and styles before contributing.
