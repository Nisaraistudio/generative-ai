# Vibe Commerce

A clean, mobile-first e-commerce starter built with Next.js, TypeScript, Tailwind CSS, and Stripe Checkout.

## Included

- Responsive storefront
- Product catalog and search/filtering
- Product detail pages
- Persistent local cart
- Quantity controls
- Stripe Checkout API route
- Supabase production database schema + RLS
- Success page
- Environment variable template

## Run locally

```bash
npm install
cp .env.example .env.local
npm run dev
```

Open http://localhost:3000.

## Stripe

Add `STRIPE_SECRET_KEY` to `.env.local`. The checkout endpoint creates a Stripe-hosted Checkout Session. Keep the secret key server-side only.

For production, add a Stripe webhook and persist paid orders in Supabase before fulfilling them.

## Supabase

Run `supabase/schema.sql` in the Supabase SQL editor. For a full production deployment, replace the demo product source with Supabase queries and add authenticated admin operations through server-side routes.

## Deployment

Deploy to Vercel:

```bash
npm run build
```

Then add the environment variables in Vercel Project Settings.

## Production checklist

1. Add Supabase product/order queries.
2. Add Supabase Auth for customer accounts.
3. Add Stripe webhook verification and order persistence.
4. Add admin dashboard with protected server routes.
5. Move product images to Supabase Storage or an image CDN.
6. Add rate limiting and abuse protection to public API routes.
7. Add analytics, SEO metadata, sitemap and robots.txt.
8. Test checkout, refunds, inventory and webhook retry behavior before launch.
