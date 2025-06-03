my-nuxt-project/
├── .nuxt/ # (Generated) Development build artifacts - DO NOT TOUCH
├── .output/ # (Generated) Production build artifacts - DO NOT TOUCH
│
├── assets/ # FRONTEND: Static assets processed by build tools (CSS, SASS, images, fonts)
│ ├── css/
│ │ └── main.css
│ └── images/
│ └── logo.png
│
├── components/ # FRONTEND: Reusable Vue components (auto-imported)
│ ├── global/ # Optional: For globally available components
│ │ └── AppHeader.vue
│ │ └── AppFooter.vue
│ ├── ui/ # Optional: For base UI elements
│ │ └── BaseButton.vue
│ │ └── BaseCard.vue
│ └── ProductCard.vue
│
├── composables/ # FRONTEND/UNIVERSAL: Vue Composition API functions (auto-imported)
│ ├── useAuth.ts
│ └── useProducts.ts
│
├── layouts/ # FRONTEND: Page layouts (auto-imported)
│ ├── default.vue # Default layout for pages
│ └── admin.vue # Custom layout for admin section
│
├── middleware/ # FRONTEND: Route middleware (runs before navigating to a route)
│ ├── auth.global.ts # Global middleware applied to all routes
│ └── analytics.ts # Named middleware for specific routes
│
├── pages/ # FRONTEND: Application views and routes (file-system routing)
│ ├── index.vue # Route: /
│ ├── about.vue # Route: /about
│ ├── products/
│ │ ├── index.vue # Route: /products
│ │ └── [id].vue # Route: /products/:id (dynamic)
│ └── admin/
│ └── dashboard.vue # Route: /admin/dashboard
│
├── plugins/ # FRONTEND/UNIVERSAL: Vue plugins and custom JS (runs before app creation)
│ ├── axios.ts # Example: Configure Axios
│ └── i18n.client.ts # Example: Internationalization (client-side only)
│
├── public/ # FRONTEND: Static assets served directly from root (no build processing)
│ ├── favicon.ico
│ └── robots.txt
│
├── server/ # BACKEND: Server-side logic (Nitro server engine)
│ ├── api/ # BACKEND: API endpoints (e.g., /api/users)
│ │ ├── hello.ts # Responds to GET /api/hello
│ │ ├── products/
│ │ │ ├── index.get.ts # Responds to GET /api/products
│ │ │ └── [id].get.ts # Responds to GET /api/products/:id
│ │ └── auth/
│ │ └── login.post.ts # Responds to POST /api/auth/login
│ │
│ ├── middleware/ # BACKEND: Server middleware (runs on every server request)
│ │ └── logger.ts # Example: Log incoming requests
│ │ └── cors.ts # Example: Configure CORS
│ │
│ ├── plugins/ # BACKEND: Nitro server plugins (e.g., connect to DB on startup)
│ │ └── database.ts
│ │
│ ├── routes/ # BACKEND: Server routes without the /api prefix
│ │ └── sitemap.xml.ts # Example: /sitemap.xml
│ │
│ └── utils/ # BACKEND: Utility functions specific to the server
│ └── db.ts # Example: Database helper functions
│
├── utils/ # FRONTEND/UNIVERSAL: General utility functions (auto-imported)
│ └── formatters.ts
│
├── app.vue # Main Vue component, entry point for your pages
├── nuxt.config.ts # Nuxt project configuration
├── package.json # Project dependencies and scripts
├── tsconfig.json # TypeScript configuration (if using TypeScript)
└── README.md # Project documentation
