# API Explorer: Mastering RESTful Connections

This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/pages/api-reference/create-next-app).

## Project Description

CineSeek is a modern movie discovery application built with **Next.js**, **TypeScript**, and **Tailwind CSS**. Users can browse movies from the MoviesDatabase API, view details, and search by year or genre. The project emphasizes responsive design, clean architecture, and robust API integration.

---

## Learning Objectives

- Understand API documentation and integration
- Implement TypeScript interfaces for API responses
- Create reusable React components
- Build responsive layouts with Tailwind CSS
- Manage state for filtering and pagination
- Handle errors and loading states effectively
- Set up Next.js API routes for server-side data fetching
- Manage environment variables for API keys

---

## Requirements

### Technical Stack

- Next.js 14 (Pages Router)
- TypeScript
- Tailwind CSS
- Font Awesome icons
- MoviesDatabase API

### Development Requirements

- Node.js (v16 or higher)
- npm or yarn
- Git

---

## File Structure

```
alx-movie-app/
├── components/
│   ├── commons/
│   │   ├── Button.tsx
│   │   ├── Loading.tsx
│   │   └── MovieCard.tsx
│   └── layouts/
│       ├── Footer.tsx
│       ├── Header.tsx
│       └── Layout.tsx
├── interfaces/
│   └── index.ts
├── pages/
│   ├── api/
│   │   └── fetch-movies.ts
│   ├── movies/
│   │   └── index.tsx
│   ├── _app.tsx
│   └── index.tsx
├── public/
├── styles/
│   └── globals.css
├── .env.local
├── .eslintrc.json
├── .gitignore
├── next.config.js
├── package.json
└── tsconfig.json
```

---

## Best Practices

### Code Quality

- Use TypeScript interfaces for all props and API responses
- Component-based architecture with clear separation of concerns
- Proper error handling in API requests
- Loading states for better UX
- Store sensitive data in environment variables

### Performance

- Client-side navigation with Next.js router
- Efficient API calls with pagination
- Responsive design with Tailwind CSS
- Image optimization using Next.js Image component

### Maintainability

- Consistent code formatting
- Clear folder structure
- Reusable components
- Comprehensive prop typing
- Proper documentation in README

---

## API Integration

**Endpoints:**

- `/titles`: Fetch movie data, filter by year/genre, supports pagination

**Authentication:**

- API key via headers
- Store API key in environment variables
- Use server-side API route to protect keys

**Error Handling:**

- Loading component for pending states
- Try/catch in API routes
- Status code checks
- Type guards for API data

**Usage Limits:**

- Consider API rate limits
- Use pagination to limit request size
- Client-side caching where appropriate
- Error boundaries for graceful failure

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/pages/building-your-application/routing/api-routes) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/pages/building-your-application/routing/api-routes) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/pages/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn-pages-router) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/pages/building-your-application/deploying) for more details.
