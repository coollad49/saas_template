
# Skill Resolution

Match the current task to the categories below. For any match, read the full SKILL.md
before proceeding. Do not read skills for unmatched categories.


**Frontend**
- Any UI component, page, or layout → `impeccable` + `web-design-guidelines`
- Any React or Next.js code → `vercel-react-best-practices` + `next-best-practices`
- Authentication integration → `better-auth-best-practices`

**Marketing & Growth**
- Ad copy or creatives → `ad-creative` + `copywriting`
- SEO audit → `seo-audit`
- AI search optimization → `ai-seo`
- Programmatic SEO pages → `programmatic-seo`
- Page conversion → `page-cro`
- Signup flow → `signup-flow-cro`
- Onboarding/activation → `onboarding-cro`
- Paywall or upsell → `paywall-upgrade-cro`
- Popup or modal → `popup-cro`
- Pricing decisions → `pricing-strategy`
- Content planning → `content-strategy`
- Social content → `social-content`
- Launch planning → `launch-strategy`
- Lead magnets → `lead-magnets`
- Referral/affiliate → `referral-program`
- Competitor research → `competitor-profiling` + `competitor-alternatives`
- Customer research → `customer-research`
- Community growth → `community-marketing`
- Sales collateral → `sales-enablement`
- Analytics setup → `analytics-tracking`
- Schema markup → `schema-markup`
- Site structure → `site-architecture`
- Marketing ideas → `marketing-ideas`
- Psychological framing in copy → `marketing-psychology`

**Workflow**
- Executing a written plan → `executing-plans` or `subagent-driven-development`
- Creating/editing Word docs → `docx`
- Image generation → `image`
- Video production → `video`

All skill files are at `~/.agents/skills/<skill-name>/SKILL.md`.

# Tooling

- Use **bun** always. Never npm, pnpm, or yarn.
- Do not run `bun run build` unless absolutely necessary (e.g., final production check)
  due to RAM constraints. Use `bunx tsc --noEmit` and Lint for static analysis instead.

---

# Architecture Preferences

- Use **Next.js Server Actions** for all data mutations and queries.
- Do **NOT** create API Routes (`app/api/*`) for application logic.
- Exception: Third-party auth handlers (e.g., Better Auth) may use routes.

---

# Documentation Guidelines

- For every feature built, a `DEVELOPER.md` file **must** be created and co-located
  with the feature's code folder — not in a central `/docs` folder.
- This file must document: architecture, seeders, debug/simulation tools, caveats,
  and any information a future developer would need to work on the feature.

---

# Testing Guidelines

- **Feature Delivery Rule**: For every feature built or modified, explicitly explain
  how to test it before considering the task complete.
- If pure business logic is involved, write Vitest unit tests.
- If the feature requires database data to be verified (UI lists, leaderboards, etc.),
  provide or write a database seeder and explain how to run it.
- Focus on pure functions and business logic — avoid UI component testing.
- Use Vitest as the test runner (`bun test` / `bun test:watch`).
- Place test files alongside source files (e.g., `retry.test.ts` next to `retry.ts`).
- Tests must run without Next.js

---