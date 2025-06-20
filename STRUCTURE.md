`anik-nuxt/`

- `├── .nuxt/` _# (Generated) Development build artifacts - DO NOT TOUCH_
- `├── .output/` _# (Generated) Production build artifacts - DO NOT TOUCH_
- `├── assets/` _# FRONTEND: Static assets processed by build tools (CSS, SASS, images, fonts)_
  - `├── css/`
    - `└── main.css`
  - `└── images/`
    - `└── logo.png`
- `├── components/` _# FRONTEND: Reusable Vue components (auto-imported)_
  - `├── global/` _# Optional: For globally available components_
    - `├── AppHeader.vue`
    - `└── AppFooter.vue`
  - `├── ui/` _# Optional: For base UI elements_
    - `├── BaseButton.vue`
    - `└── BaseCard.vue`
  - `└── ProductCard.vue`
- `├── composables/` _# FRONTEND/UNIVERSAL: Vue Composition API functions (auto-imported)_
  - `├── useAuth.ts`
  - `└── useProducts.ts`
- `├── layouts/` _# FRONTEND: Page layouts (auto-imported)_
  - `├── default.vue` _# Default layout for pages_
  - `└── admin.vue` _# Custom layout for admin section_
- `├── middleware/` _# FRONTEND: Route middleware (runs before navigating to a route)_
  - `├── auth.global.ts` _# Global middleware applied to all routes_
  - `└── analytics.ts` _# Named middleware for specific routes_
- `├── pages/` _# FRONTEND: Application views and routes (file-system routing)_
  - `├── index.vue` _# Route: /_
  - `├── about.vue` _# Route: /about_
  - `├── products/`
    - `├── index.vue` _# Route: /products_
    - `└── [id].vue` _# Route: /products/:id (dynamic)_
  - `└── admin/`
    - `└── dashboard.vue` _# Route: /admin/dashboard_
- `├── plugins/` _# FRONTEND/UNIVERSAL: Vue plugins and custom JS (runs before app creation)_
  - `├── axios.ts` _# Example: Configure Axios_
  - `└── i18n.client.ts` _# Example: Internationalization (client-side only)_
- `├── public/` _# FRONTEND: Static assets served directly from root (no build processing)_
  - `├── favicon.ico`
  - `└── robots.txt`
- `├── server/` _# BACKEND: Server-side logic (Nitro server engine)_
  - `├── api/` _# BACKEND: API endpoints (e.g., /api/users)_
    - `├── hello.ts` _# Responds to GET /api/hello_
    - `├── products/`
      - `├── index.get.ts` _# Responds to GET /api/products_
      - `└── [id].get.ts` _# Responds to GET /api/products/:id_
    - `└── auth/`
      - `└── login.post.ts` _# Responds to POST /api/auth/login_
  - `├── middleware/` _# BACKEND: Server middleware (runs on every server request)_
    - `├── logger.ts` _# Example: Log incoming requests_
    - `└── cors.ts` _# Example: Configure CORS_
  - `├── plugins/` _# BACKEND: Nitro server plugins (e.g., connect to DB on startup)_
    - `└── database.ts`
  - `├── routes/` _# BACKEND: Server routes without the /api prefix_
    - `└── sitemap.xml.ts` _# Example: /sitemap.xml_
  - `└── utils/` _# BACKEND: Utility functions specific to the server_
    - `└── db.ts` _# Example: Database helper functions_
- `├── utils/` _# FRONTEND/UNIVERSAL: General utility functions (auto-imported)_
  - `└── formatters.ts`
- `├── app.vue` _# Main Vue component, entry point for your pages_
- `├── nuxt.config.ts` _# Nuxt project configuration_
- `├── package.json` _# Project dependencies and scripts_
- `├── tsconfig.json` _# TypeScript configuration (if using TypeScript)_
- `└── README.md` _# Project documentation_
