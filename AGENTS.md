# 1. Language & Syntax Rules (High Priority)

- Use **TypeScript** for all new code.
- Do NOT use `var`. Only use `let` or `const`.
- Prefer functional components over class components.
- Use arrow functions `const func = () => {}` by default.
- Use modern syntax: spread operators (`...`), destructuring, optional chaining (`?.`), and nullish coalescing (`??`).
- Use **ESLint** and **Prettier** for code formatting.
- Do not write `console.log`, `console.warn`, or `console.error`. Use the built-in `logger` utilities.

# 2. React & Next.js Rules

- **Next.js 14+**: Use **App Router** (not Pages Router).
- **Components**: Create components in `src/components/`.
- **Server Components vs. Client Components**: Only mark a component as a "use client" if it needs browser APIs (state, effects, event handlers).
- **Imports**: Use absolute imports: `import { Button } from "@/components/ui/button"`.
- **Styling**:
  - Use **Tailwind CSS**.
  - Avoid custom CSS classes unless necessary.
  - Use `cn()` utility for merging Tailwind classes.
- **Folder Structure**: Follow the [Atomic Design](https://atomicdesign.bradfrost.com/) principles (optional) but keep it flat and organized.

# 3. TypeScript Rules

- **No `any` Type**: Avoid `any` at all costs. Use `unknown` if the type is uncertain.
- **Strict Mode**: Ensure `strict` mode is enabled in `tsconfig.json`.
- **Utility Types**: Leverage TypeScript utility types (`Partial`, `Pick`, `Omit`, `Record`, `Awaited`).
- **Interfaces vs. Types**: Use `interface` for object shapes and API responses. Use `type` for unions, intersections, and mapped types.
- **Enums**: Prefer `string enums` over numeric enums for better readability and debugging.

# 4. State Management Rules

- **Local State**: Use `useState` for simple UI state.
- **Server State**: Use **TanStack Query (React Query)** for API data fetching, caching, and synchronization.
- **Global State**: Use **Zustand** or **Redux Toolkit** for shared application state.
- **Avoid Prop Drilling**: Use Context API or a global state manager when props need to be passed through many layers.

# 5. API & Data Rules

- **API Client**: Use the centralized API client in `src/lib/api-client.ts`.
- **HTTP Methods**: Adhere to RESTful conventions (GET, POST, PUT, DELETE).
- **Error Handling**: Implement robust error handling. Don't let errors crash the app. Show user-friendly messages.
- **Data Fetching**:
  - Use **React Query** for fetching and caching.
  - Use **SWR** for simple or real-time data.
- **Async Operations**: Use **async/await** for cleaner asynchronous code.

# 6. Security Rules

- **Never commit secrets** to git (e.g., API keys, passwords).
- Use `.env` files for environment variables.
- Sanitize all user inputs to prevent XSS attacks.
- Use prepared statements or ORM for database interactions to prevent SQL injection.
- Implement proper authentication and authorization checks.

# 7. Testing Rules

- **Unit Tests**: Use **Vitest** for fast unit testing.
- **Component Tests**: Use **React Testing Library** for component testing.
- **E2E Tests**: Use **Playwright** for end-to-end testing.
- **Mocking**: Use **MSW (Mock Service Worker)** for API mocking.

# 8. Performance Rules

- **Code Splitting**: Use Next.js dynamic imports (`next/dynamic`) for large components.
- **Memoization**: Use `React.memo`, `useMemo`, and `useCallback` to prevent unnecessary re-renders.
- **Lazy Loading**: Lazy load images and components.
- **Pagination**: Implement pagination for large datasets.
- **Virtual Scrolling**: Use `react-window` or `tanstack-virtual` for long lists.

# 9. SEO Rules

- Use **Next.js Metadata API** (`metadata` export) for SEO optimization.
- Set proper `title`, `description`, and `keywords` for each page.
- Use semantic HTML5 tags.
- Implement Open Graph tags for social media sharing.

# 10. Accessibility (A11y) Rules

- Use semantic HTML.
- Ensure proper ARIA roles and labels.
- Provide keyboard navigation support.
- Use descriptive alt text for images.
- Ensure sufficient color contrast.

# 11. Naming Conventions

- **Components**: PascalCase (e.g., `UserProfileCard.tsx`).
- **Constants**: UPPER_SNAKE_CASE (e.g., `MAX_ITEMS`).
- **Variables/Functions**: camelCase (e.g., `calculateTotalAmount`).
- **File Names**: Use kebab-case for non-component files (e.g., `date-utils.ts`).

# 12. Project Setup Rules

- **Monorepo**: Use **Turborepo** for managing multiple packages/apps.
- **Package Manager**: Use **pnpm**.
- **CI/CD**: Set up **GitHub Actions** for automated testing and deployment.

# 13. Documentation Rules

- **Inline Comments**: Use JSDoc for complex functions and components.
- **README**: Maintain a comprehensive `README.md`.
- **Changelog**: Keep a `CHANGELOG.md` updated with significant changes.

# 14. Code Quality Rules

- **DRY Principle**: Don't Repeat Yourself. Extract reusable code into utilities or components.
- **Single Responsibility**: Each component/function should do one thing well.
- **KISS Principle**: Keep It Simple, Stupid.
- **YAGNI Principle**: You Ain't Gonna Need This. Don't add functionality prematurely.

# 15. Version Control Rules

- **Branch Naming**: Use [Conventional Commits](https://www.conventionalcommits.org/) (e.g., `feat: add user authentication`).
- **Commit Messages**: Write clear, concise commit messages.
- **PR Templates**: Use Pull Request templates.
- **Squash Merges**: Squash all feature branches into main.

# 16. Mobile Responsiveness Rules

- Use **Mobile-First** approach in Tailwind CSS.
- Test on various screen sizes.
- Use relative units (%, rem, em) instead of fixed pixels.

# 17. Internationalization (i18n) Rules

- Use **next-intl** for i18n implementation.
- Separate translations into locale files.
- Use `useTranslations` hook to get translation functions.
- Use `lang-switcher` for language switching.

# 18. Styling Rules

- **Tailwind First**: Prefer Tailwind utility classes over custom CSS.
- **Custom CSS**: Only use custom CSS when necessary, and place it in the `components/ui/` or `assets/styles/` directory.
- **Inline Styles**: Avoid inline styles unless absolutely necessary (e.g., dynamic values).
- **CSS Modules**: Consider using CSS Modules for component-specific styles.

# 19. Component Rules

- **Component Organization**: Create components in `components/` directory with proper subdirectories.
- **File Naming**: Use PascalCase for component files (e.g., `UserProfileCard.tsx`).
- **Props Interface**: Define an interface or type for component props (e.g., `interface UserProfileCardProps { ... }`).
- **Default Props**: Use default values for optional props.
- **Memoization**: Use `React.memo` for components that might cause unnecessary re-renders.

# 20. Performance Rules

- **Code Splitting**: Use Next.js dynamic imports (`next/dynamic`) for large components or pages.
- **Lazy Loading**: Implement lazy loading for images and non-critical components.
- **Memoization**: Use `React.memo`, `useMemo`, and `useCallback` to prevent unnecessary re-renders.
- **Pagination**: Implement pagination for large datasets.
- **Virtual Scrolling**: Use `react-window` or `tanstack-virtual` for long lists.
- **Image Optimization**: Use `next/image` for optimized image loading.

# 21. SEO Rules

- Use **Next.js Metadata API** (`metadata` export) for SEO optimization.
- Set proper `title`, `description`, and `keywords` for each page.
- Use semantic HTML5 tags.
-
