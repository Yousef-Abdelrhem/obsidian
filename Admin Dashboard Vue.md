## ==Project Overview:==
Admin Dashboard Vue is a modern, responsive admin dashboard built with Vue.js, designed
specifically for e-commerce administrators to manage products, orders, customers, and inventory
efficiently. The dashboard provides secure authentication and a clean UI using Tailwind CSS,
making daily operations intuitive and fast.
## ==Project Objectives:==
- Simplify the management of online store data (products, customers, orders).
- Provide a robust backend with MongoDB and Express.js.
- Deliver a responsive and elegant admin UI with Vue.js and Tailwind CSS.
- Enable secure user login and authorization features.
- Use a scalable architecture with state management via Pinia.
## ==Technology Stack:==
## ==Frontend:==
- Vue.js
- Vue Router
- Pinia
- Axios
- Tailwind CSS
## ==Backend:==
- Node.js
- Express.js
- MongoDB
## ==Key Features:==
## ==User Features:==
- Product Management: Add, edit, and delete product records.
- Order Tracking: View, filter, and update order statuses.
- Customer Management: Maintain customer data and history.
- Inventory Control: Monitor stock levels and alert low inventory.
- Authentication: Secure login and user authorization system.
- Responsive Design: Optimized for all devices.
## ==User Flow:==
1. Login Page -> User authentication with protected dashboard routes.
2. Dashboard Landing -> Overview of metrics and shortcut links to core features.
3. Products Module -> List, edit, delete, and add new products.
4. Orders Module -> Track and update order statuses.
5. Customers Module -> View and manage customer details.
6. Inventory Module -> Real-time stock monitoring and control.
## ==Frontend Structure:==
/src
- components/ : Reusable components (Navbar, Table, Form)
- views/ : Page-level views (Dashboard, Products, Orders)
- router/ : Vue Router setup and protected routes
- store/ : Pinia state modules (auth, products, orders)
- services/ : Axios API integration
- assets/ : Static assets (icons, images)
- App.vue : Root component
- main.js : Application entry point
## ==Backend Structure:==
/server
- routes/ : API routes (auth, products, orders, customers)
- controllers/ : Route logic handlers
- models/ : Mongoose schemas (User, Product, Order)
- middlewares/ : Auth checks, error handling
- config/ : DB and environment setup
## ==API Endpoints Overview:==
Resource Endpoint Description
Auth /api/auth Register, Login, Token verification
Products /api/products CRUD operations
Orders /api/orders View, filter, update order status
Customers /api/customers Manage customer data
Getting Started:
Prerequisites:
- Node.js v16+
- npm v8+
- MongoDB instance
- Vue CLI (optional)
## ==Installation:==
git clone https://github.com/Yousef-Abdelrhem/AdminDashboard.git
cd frontend
npm install
npm run dev
cd ../backend
npm install
npm run dev
## ==Future Enhancements:==
- Role-based access control (RBAC)
- Dashboard analytics with charts
- Email notifications for orders
- Multi-language support (EN/AR)
- Dark mode toggle
## ==Testing & QA:==
- API Testing with Postman
- Unit Testing with Vue Test Utils
- Manual QA for responsive design and flows
- Integration testing for critical workflows
==Acknowledgments:==
- Vue.js Core Team
- Tailwind CSS Contributors
- Axios for API requests
- MongoDB/Mongoose for database models