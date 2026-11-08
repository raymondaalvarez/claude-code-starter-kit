# <Project name>

<One or two sentences: what this app does and who uses it.>

## Stack
- <Framework, e.g. Next.js 15 (App Router)>
- <Database / auth, e.g. Supabase>
- <Payments, hosting, e.g. Stripe, Vercel>

## Commands
- Dev server: `<npm run dev>`
- Tests: `<npm test>`
- Typecheck / lint: `<npm run typecheck && npm run lint>`
Run the typecheck and tests before saying a change is done.

## Rules
- Never put secrets in client code or in `NEXT_PUBLIC_` / `VITE_` variables.
- Secret and service-role keys are used only in server code.
- Every Supabase table has Row Level Security on, with policies.
- Navigation uses `<a href>` links (or the framework's Link component), never onClick-only buttons.
- Each page sets its own `<title>` and meta description.
- Ask before adding a dependency, changing the database schema, or deleting files.
- <Your naming and folder conventions>

## Where things live
- <app/ → routes>
- <lib/ → shared helpers>
- <supabase/migrations/ → schema changes>
