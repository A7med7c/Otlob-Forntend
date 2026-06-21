# Talabak

![Angular](https://img.shields.io/badge/Angular-21-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![SSR](https://img.shields.io/badge/SSR-Enabled-0F172A?style=for-the-badge&logo=angular&logoColor=white)
![NgRx](https://img.shields.io/badge/NgRx-Architecture%20Ready-BA2BD2?style=for-the-badge&logo=ngrx&logoColor=white)
![Signals](https://img.shields.io/badge/Signals-Angular%20Signals-0EA5E9?style=for-the-badge&logo=angular&logoColor=white)
![RxJS](https://img.shields.io/badge/RxJS-Reactive%20Programming-B7178C?style=for-the-badge&logo=reactivex&logoColor=white)
![i18n](https://img.shields.io/badge/i18n-ngx--translate-16A34A?style=for-the-badge&logo=googletranslate&logoColor=white)
![JWT Authentication](https://img.shields.io/badge/JWT-Authentication-111827?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

Talabak is a production-style Angular 21 e-commerce storefront built to demonstrate modern frontend engineering practices for recruiters, hiring managers, and portfolio reviewers. The project showcases a standalone Angular architecture, Server-Side Rendering (SSR), hydration, internationalization, JWT-based authentication, signal-driven UI state, and a responsive shopping experience designed for both English and Arabic users.

This repository is positioned as a portfolio-ready example of how to build a scalable Angular application with clean separation of concerns, feature-oriented structure, reusable services, and user-focused UX patterns.

## Project Overview

Talabak delivers a complete storefront journey: authentication, product discovery, product details, cart management, checkout initiation, wishlist handling, and order history. It is implemented with Angular standalone components and lazy-loaded routes, integrates with a remote e-commerce API, and applies modern Angular capabilities such as signals, computed signals, functional guards, HTTP interceptors, hydration, and view transitions.

From a portfolio perspective, the project demonstrates not only UI implementation, but also architectural thinking, route security, API integration, localization, loading/error handling, and production-minded frontend patterns.

## Features

- User authentication with registration, login, logout, and forgot-password flow
- JWT-based session handling with route protection
- Product browsing with category and brand exploration
- Product search and product detail pages
- Shopping cart management with add, update, remove, and clear actions
- Checkout session integration
- Order history retrieval
- Wishlist management
- English and Arabic localization
- RTL/LTR switching for bilingual UX
- Global loading spinner during HTTP activity
- Toast-based success and error notifications
- Responsive UI built with Bootstrap 5
- SSR-enabled Angular application with hydration support

## Technical Highlights

Talabak is designed to present production-ready Angular development practices, including:

- **Angular 21 architecture** using standalone components instead of traditional NgModules
- **Lazy-loaded route composition** through `loadComponent` for feature delivery and bundle efficiency
- **Signal-based UI state** for authentication, cart counters, loading states, and view-level reactivity
- **Computed signals** for derived UI values such as cart state and navigation indicators
- **Reactive programming with RxJS** for HTTP flows, subscriptions, and async UI behavior
- **SSR + hydration** to improve initial rendering strategy and modern Angular app delivery
- **Functional guards and interceptors** for secure navigation and centralized cross-cutting concerns
- **Global user experience patterns** such as spinners, toast notifications, and resilient error handling
- **Internationalized, RTL-aware UI** suitable for Arabic and English audiences
- **Feature-oriented code organization** that keeps business concerns separated and maintainable

## Architecture

Talabak follows a layered frontend structure that keeps responsibilities clear and the application easy to extend.

### Core Layer Responsibilities

The `Core` layer acts as the application-wide foundation and contains the responsibilities a traditional Angular `CoreModule` would typically own:

- API-facing services for authentication, products, cart, wishlist, orders, categories, translation, and storage
- Functional route guards for authentication and logged-in state handling
- HTTP interceptors for auth headers, loading indicators, and centralized error handling
- Shared interfaces and utility abstractions used across features
- Environment-based configuration for API and frontend URLs

### Shared UI Responsibilities

Reusable UI concerns are handled through shared layouts and cross-application components, including:

- Authentication and main application layouts
- Navigation components for authenticated and public flows
- Footer and shared UX elements
- Reusable visual behavior such as global loading and notification patterns

### Feature-Based Structure

The project is organized by feature/page responsibility under `Components`, which keeps the codebase easy to navigate for portfolio reviewers and future collaborators. Major features include:

- Authentication
- Home / storefront
- Products
- Categories
- Brands
- Cart
- Wishlist
- Checkout / place order
- Order history
- Not found handling

### Services

Services are used as the primary business logic and integration layer. They encapsulate API communication, state coordination, translation behavior, token access, and application-wide concerns rather than pushing logic into components.

### Guards

Functional guards protect authenticated routes and redirect users appropriately depending on whether a JWT token is available.

### Interceptors

Interceptors centralize:

- protected-route token injection
- loading spinner orchestration
- API error normalization and user-friendly toast feedback

### Environment Configuration

Environment values are maintained in `src/app/Core/Environments/environment.ts` and currently define the API base URL and frontend URL used by checkout and HTTP integrations.

## Angular Concepts Demonstrated

This project highlights a broad range of Angular-specific skills:

- Angular 21 application setup
- Standalone Components
- Angular Signals
- Computed Signals
- Signal-based state management
- RxJS Observables
- Reactive Programming
- Dependency Injection
- Functional Guards
- Route Protection
- HTTP Interceptors
- Lazy Loading with `loadComponent`
- Server-Side Rendering (SSR)
- Hydration with event replay
- View Transitions
- Internationalization with `ngx-translate`
- Reactive Forms
- Custom Validators
- Component communication through services and reactive state
- Service-oriented architecture
- Error handling strategies
- Loading state management
- Toast notifications
- API integration
- JWT authentication
- Local Storage management
- Responsive design
- RTL/LTR support

## State Management

Talabak currently uses **signal-based state management** and service-driven orchestration rather than a full NgRx store implementation.

### Current Approach

- Angular Signals are used to manage local and shared UI state such as authentication state, user data, cart item count, loading flags, success flags, and page-level data collections
- Computed signals are used for derived state such as cart emptiness and reactive navigation values
- RxJS Observables are used for API integration and asynchronous event streams
- Services act as a coordination boundary between components and backend APIs

### NgRx Positioning

NgRx is **not currently implemented**, but the project is structured in a way that can scale into NgRx when feature complexity grows. The existing service boundaries and feature-oriented routing would support the introduction of:

- **Store** for centralized feature state
- **Actions** for explicit state transitions
- **Effects** for async workflows and side effects
- **Selectors** for memoized derived state

This makes Talabak a strong example of an application that already demonstrates state design awareness while using lightweight Angular-native state patterns first.

## Authentication & Security

Authentication and route security are implemented with portfolio-relevant Angular patterns:

- JWT-based authentication flow for signup, signin, and password reset
- Token persistence in browser storage
- Route access control through functional guards
- Auth-aware redirects for public vs. protected areas
- HTTP interceptor for attaching tokens to protected API requests
- Client-side decoded user session handling
- Centralized error interception for failed API responses

## Internationalization (i18n)

Talabak includes bilingual UX support using `ngx-translate`:

- English and Arabic translation files stored under `public/i18n`
- Runtime language switching
- Persisted language preference in local storage
- Automatic document `lang` and `dir` updates
- RTL/LTR support for Arabic and English layouts

This is especially valuable for demonstrating real-world frontend readiness in multilingual products.

## Performance Optimizations

The project includes several performance-conscious decisions:

- **SSR** for server-rendered delivery
- **Hydration** for client takeover after server rendering
- **Lazy Loading** through route-level component loading
- **Optimized Change Detection** with `ChangeDetectionStrategy.OnPush` in key UI areas
- **Caching-friendly bundle output** using production hashing
- **Bundle optimization** through Angular production build settings and route splitting
- **View transitions** for smoother navigation experience

While a dedicated client-side data caching layer is not yet implemented, the application structure is prepared for service-level caching or future state-store memoization strategies.

## Tech Stack

### Frontend

- Angular 21
- TypeScript
- RxJS
- Bootstrap 5
- SCSS
- Font Awesome

### Angular Ecosystem & Libraries

- Angular SSR
- Angular Router
- Angular Reactive Forms
- Angular Signals
- `@ngx-translate/core`
- `@ngx-translate/http-loader`
- `ngx-spinner`
- `ngx-toastr`
- `ngx-owl-carousel-o`
- `jwt-decode`

### Runtime / Tooling

- Node.js
- npm
- Angular CLI
- Vitest / Angular unit test builder
- Prettier

## Project Structure

```text
Talabak/
+-- public/
|   +-- i18n/                   # Translation JSON files
|   +-- images/                 # Static assets
+-- src/
|   +-- app/
|   |   +-- Components/         # Feature/page standalone components
|   |   +-- Core/
|   |   |   +-- Environments/   # API and frontend configuration
|   |   |   +-- Guards/         # Functional route guards
|   |   |   +-- Interceptors/   # HTTP cross-cutting concerns
|   |   |   +-- Interfaces/     # Shared TypeScript contracts
|   |   |   +-- Pipes/          # Reusable transformation logic
|   |   |   +-- Services/       # Business logic and API integration
|   |   +-- Layouts/            # Auth and application layouts
|   |   +-- app.config.ts       # Global Angular providers
|   |   +-- app.routes.ts       # Lazy-loaded route definitions
|   +-- main.ts                 # Browser bootstrap
|   +-- main.server.ts          # Server bootstrap
|   +-- server.ts               # SSR server entry
+-- angular.json
+-- package.json
+-- README.md
```

## Installation

### Prerequisites

- Node.js 20+ recommended
- npm 11+ recommended
- Angular CLI optional for local Angular commands

### Setup

```bash
npm install
```

### Run Development Server

```bash
npm start
```

Open `http://localhost:4200/`.

### Production Build

```bash
npm run build
```

### Run Unit Tests

```bash
npm test
```

## Environment Configuration

The main environment settings are defined in:

- `src/app/Core/Environments/environment.ts`

Current values include:

- `baseUrl` for the e-commerce API
- `frontUrl` for the frontend callback/checkout return flow

If you need to point Talabak to a different backend, update the `baseUrl` value accordingly.

## Available Scripts

| Script | Description |
|--------|-------------|
| `npm start` | Starts the Angular development server |
| `npm run build` | Creates the production build with SSR output |
| `npm run watch` | Runs development build in watch mode |
| `npm test` | Executes the unit test suite |
| `npm run serve:ssr:E-commerce-Angular` | Serves the generated SSR build |


