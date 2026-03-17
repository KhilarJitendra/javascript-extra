# Frontend Interview Notes – Jitendra Khilar

---

## 1. Owned frontend development of multiple critical user flows within a large-scale luxury e-commerce
platform serving international markets, built with React and Next.js.

- When I say owned, I mean I was responsible end-to-end—from understanding requirements, designing the UI architecture, implementing components, handling API integration, to ensuring performance and production stability.

- Some of the key flows I worked on include the product detail page, cart management (adding/removing items, updating quantities, persisting cart state, and ensuring pricing, availability, and totals are always accurate), and a complex multi-step checkout flow.

### Follow-up Questions

**Q: What does “ownership” mean in your role?**  
A: End-to-end responsibility including requirement understanding, architecture design, development, API integration, and ensuring production stability.

**Q: What were the most critical flows?**  
A: Product detail page, cart management, and checkout flow.

**Q: What challenges did you face?**  
A: Managing state consistency and handling edge cases across flows.

---

## 2. Designed and maintained a monorepo architecture with 150+ reusable React components and 70+
custom hooks, improving UI consistency and developer velocity across teams.

- Why Monorepo ?  
  - A monorepo is a single repository that contains multiple projects or modules like UI components, hooks, and applications—instead of having separate repositories for each.

- As the application scaled, we started facing issues like duplicated code and inconsistent UI across teams.

- To address this, I designed and maintained a monorepo architecture where all shared components, hooks, and utilities were centralized.

- We built over 150 reusable React components, following a design system approach—covering elements like buttons, modals, product cards, and layouts.

- Along with that, I developed 70+ custom hooks to abstract common logic such as API handling, cart state, authentication, and form management.

### Follow-up Questions

**Q: Why monorepo over multi-repo?**  
A: Easier code sharing, better consistency, and centralized dependency management.

**Q: How did you structure it?**  
A: Separate packages for UI components, hooks, utilities, and applications.

**Q: What challenges did you face?**  
A: Dependency management and avoiding tight coupling between modules.

---

## 3. Designed a scalable frontend component system and design abstractions, reducing feature development
time by ~40%.

- As the application scaled, we started seeing inconsistencies and duplicated UI across teams.

- To address this, I designed a scalable component system with reusable and standardized UI components like buttons, inputs, modals, and layout primitives.

- I also introduced design abstractions by building flexible, configurable components—for example, instead of multiple button variants, we created a single Button component driven by props like variant, size, and state.

- This made the system scalable and easy to extend, and significantly improved development speed since teams could reuse existing building blocks instead of creating new ones.

- Overall, this reduced feature development time by around 40%.

### Follow-up Questions

**Q: What are design abstractions?**  
A: Creating flexible, configurable components using props instead of hardcoding multiple variants.

**Q: Difference between reusable components and a component system?**  
A: A component system focuses on standardization, scalability, and consistency across the application.

**Q: How did you measure 40% improvement?**  
A: Based on faster feature delivery and reduced development effort across teams.

---

## 4. Owned frontend performance initiatives, achieving 90+ Lighthouse scores through code-splitting, PWA
implementation, service workers, and advanced caching strategies.

- As the application scaled, we started facing performance issues like slow load times and large bundle sizes.

- I took ownership of frontend performance and worked on improving key metrics like Lighthouse scores and Core Web Vitals.

- We implemented code-splitting using dynamic imports to reduce the initial bundle size, and leveraged Next.js features for optimized loading.

- We also enabled PWA capabilities and used service workers to cache static assets and API responses, improving repeat visit performance and enabling offline support.

- Additionally, we applied advanced caching strategies like browser caching and stale-while-revalidate to reduce latency.

- As a result, we achieved Lighthouse scores of 90+ and significantly improved load times and overall user experience.

### Follow-up Questions

**Q: What are Core Web Vitals?**  
A: LCP (loading), FID (interactivity), CLS (layout stability).

**Q: How did you reduce bundle size?**  
A: Code splitting, lazy loading, and removing unused dependencies.

**Q: What caching strategy did you use?**  
A: Stale-while-revalidate, browser caching, and CDN caching.

---

## 5. Built and optimized a complex multi-step checkout flow, supporting address management across 15+
countries and 20+ shipping methods.

I worked on building a complex multi-step checkout flow, which is a critical part of the e-commerce experience.

The flow included steps like cart review, address entry, shipping selection, payment, and order review.

I handled the frontend architecture and implementation, including managing state across steps, integrating APIs, and ensuring a smooth user experience.

One of the main challenges was supporting 15+ countries, each with different address formats and validation rules, along with 20+ shipping methods that varied based on location and product type.

The UI was highly dynamic—for example, changing the country would update address fields and available shipping options in real time.

I also handled various edge cases like invalid addresses, unsupported regions, and payment failures.

Additionally, I optimized the flow for performance and responsiveness, ensuring fast transitions between steps.

This resulted in a scalable and reliable checkout experience that directly impacts conversion rates.

### Follow-up Questions

**Q: How did you manage state across steps?**  
A: Using centralized state management to persist data across steps.

**Q: How did you handle validation?**  
A: Step-level validation before allowing users to proceed.

**Q: Biggest challenge?**  
A: Handling dynamic behavior across countries while maintaining consistent state.

---

## 6. Implemented a robust frontend testing strategy using Playwright, achieving 95%+ end to end (E2E)
coverage and reducing production defects by ~60%.

- What is Playwright and what is E2E testing:  
  https://github.com/KhilarJitendra/javascript-extra/blob/main/playwright.md

End-to-End testing validates complete user journeys by simulating real user behavior, such as browsing products and completing checkout.

We used Playwright for E2E testing because it provides reliable browser automation, cross-browser support, and handles modern frontend applications well.

Alongside that, we used Jest for unit and integration testing of components and business logic.

We focused on testing critical flows like cart and checkout, ensuring both functionality and integration with backend services.

These tests were integrated into our CI/CD pipeline, where they ran automatically on every commit, preventing broken code from reaching production.

### Follow-up Questions

**Q: What is E2E testing?**  
A: Testing complete user journeys from start to end.

**Q: Why Playwright?**  
A: Cross-browser support, reliability, and modern app compatibility.

**Q: How did you reduce flaky tests?**  
A: Proper waits, stable selectors, and mocking unstable APIs.

**Q: How is it used in CI/CD?**  
A: Tests run automatically on every commit before deployment.

---

## 7. Developed a multi-locale and multi-language frontend platform supporting 10+ regions and 1000+
translation keys using dynamic content integrations.

The platform served multiple international markets, so I developed a multi-locale and multi-language frontend system supporting 10+ regions.

This included handling both language translations and locale-specific configurations like currency and formatting.

We managed 1000+ translation keys using a structured key-based approach, where content was dynamically loaded based on the user’s locale.

We also integrated dynamic content from backend/CMS systems, allowing translations and product data to be managed without code changes.

Using Next.js and libraries like next-intl, we implemented locale-based routing and ensured proper SSR support.

The UI dynamically adapted to the user’s region, including text, currency, and formatting.

One of the key challenges was managing translation consistency and fallback handling, which we solved through structured key management and default locales.

This enabled a seamless and localized experience for users across global markets.

### Follow-up Questions

**Q: Difference between locale and language?**  
A: Language is translation, locale includes regional formats like currency and date.

**Q: How did you manage translations?**  
A: Key-based system with dynamic loading and CMS integration.

**Q: How did you handle missing translations?**  
A: Fallback to default language (e.g., English).

---

## 8. Integrated multiple global payment methods (Adyen, PayPal, Apple Pay, Google Pay, WeChat Pay,
Alipay), ensuring seamless and localized user experiences.

As part of the checkout system, I integrated multiple global payment methods to support users across different regions.

I handled the frontend integration, including rendering payment options, managing user interactions, and handling different payment flows.

We supported providers like Adyen, PayPal, Apple Pay, Google Pay, WeChat Pay, and Alipay, with availability based on the user’s region.

One of the key challenges was that each provider had a different flow—some required redirects, while others used embedded SDKs or native popups.

The UI dynamically adapted based on the selected payment method to ensure a consistent experience.

I also handled edge cases like payment failures, cancellations, and retries with proper error handling.

The frontend worked closely with backend services for secure payment processing and order confirmation.

Overall, this enabled a seamless and localized payment experience for global users.

### Follow-up Questions

**Q: Did frontend handle payment processing?**  
A: No, frontend handled UI and interactions; backend/payment providers handled secure processing.

**Q: How did you handle failures?**  
A: Proper error handling, retries, and preserving user state.

**Q: Biggest challenge?**  
A: Handling different payment flows while maintaining consistent UX.

---

## 9. Established frontend code quality standards using ESLint, Prettier, and Husky, maintaining high
consistency across 50k+ lines of frontend code.

As the codebase grew to over 50k lines with multiple developers contributing, we started facing inconsistencies in code style and quality.

To address this, I established frontend code quality standards using ESLint for enforcing coding rules and catching potential issues, Prettier for consistent formatting, and Husky to run these checks before commits.

We integrated these into pre-commit hooks so that only properly formatted and linted code could be pushed to the repository.

This significantly improved code consistency, reduced code review overhead, and made the codebase easier to maintain at scale.

### Follow-up Questions

**Q: Why ESLint and Prettier both?**  
A: ESLint for code quality, Prettier for formatting.

**Q: What is Husky used for?**  
A: Running pre-commit hooks to enforce standards.

**Q: What if someone bypasses it?**  
A: CI pipeline enforces checks before merging.

---
