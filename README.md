# Awesome-Checkout-Customization

# Awesome-Checkout-Customization
**Top Checkout Customization (Opensource) 🌟 Star if you like it! 🌟**

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on Checkout Logic, Pricing Rules, Discount Engines, Post-Purchase Upsells & Cart Validation*
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Checkout Customization**. These tools enable merchants to control what happens at the final step of purchase—applying conditional discounts, modifying shipping rates, filtering payment methods, presenting upsells, and enforcing validation rules—from proprietary Shopify Plus tools and third-party apps to self-hosted promotion engines and composable commerce frameworks that give developers full control over checkout logic.

**Examples** include Shopify Scripts, Bold Custom Pricing, Discount Ninja, CartHook, Rebuy Engine, Fast Simon, and various Dynamic Pricing apps (the category leaders in commercial space).

**Open-source emphasis**: This section is expanded with every relevant project for self-hosting, promotion engines, and open checkout frameworks. **Critical note**: True open-source checkout customization for **Shopify specifically** is extremely limited—Shopify's checkout is a closed, hosted environment where only apps, Functions, and UI Extensions can operate. The open-source projects below address **composable commerce platforms** (Medusa, Saleor, Spree, Vendure, Sylius) where checkout is yours to modify, plus a dedicated open-source promotion engine. **None of these plug into Shopify's checkout directly.**

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Shopify Scripts](https://shopify.dev/docs/apps/checkout)** (**Sunsetting June 30, 2026**)
  **Ruby-based checkout logic engine for Shopify Plus** allowing line item, shipping, and payment customization. **Critical**: Shopify Scripts stopped accepting new edits on April 15, 2026, and **stopped executing entirely on June 30, 2026** . Any store still relying on Scripts is running frozen code with no fix path. Migration to **Shopify Functions** or supported apps is mandatory, not optional . **Pricing**: Included with Shopify Plus (from $2,300/month). **Free tier**: None. **Best for**: **legacy reference only—do not build new logic on Scripts**. If you have existing Scripts, audit them immediately and rebuild in Functions .

- **[Bold Custom Pricing](https://www.boldcommerce.com/)**
  **Customer-specific and quantity-based pricing app** for Shopify. Uses customer tags to assign wholesale, VIP, or group pricing; supports percentage, amount off, or fixed price discounts; quantity breaks; auto-tagging by country or order history; CSV import for detailed pricing . **Pricing**: **Essential** $29/month (1–10 tags), **Standard** $69/month, **Complete** $129/month (detailed pricing, CSV, POS) . **Free tier**: 14-day trial. **Best for**: Shopify merchants needing B2B/wholesale pricing tiers without custom development.

- **[Discount Ninja](https://apps.shopify.com/discount-url)**
  **Promotion engine app for Shopify** with advanced discount stacking, automatic promo items, and complex rule combinations. Users report it fills gaps in Shopify's native discount limitations . **Pricing**: Quote-only; per-month fee based on plan. **Free tier**: Trial available. **Best for**: merchants needing sophisticated promotion logic (bundles, auto-add gifts, stacked discounts) beyond Shopify's built-in capabilities.

- **[CartHook](https://carthook.com/)**
  **Post-purchase upsell platform for Shopify** with no-code drag-and-drop offer builder, A/B testing, and one-click upsell acceptance. Claims ROI of 1700% (every $100 spent returns $1,700 in upsells) . **Pricing**: Quote-only; based on monthly order volume. **Free tier**: None. **Best for**: Shopify merchants wanting to increase AOV with post-purchase offers without disrupting the initial checkout flow.

- **[Rebuy Engine](https://rebuyengine.com/)**
  **Personalization and upsell engine** with Smart Links that add items to cart via URL arguments (variant IDs, quantity, discount code, redirect destination) . **Pricing**: Quote-only. **Free tier**: None. **Best for**: merchants wanting cart manipulation and personalized upsells via URL-based smart links.

- **[Fast Simon](https://www.fastsimon.com/)**
  **Search, merchandising, and personalization SDK** for e-commerce. Provides JavaScript SDK and NPM package for integration; focuses on product discovery rather than checkout logic directly . **Pricing**: Quote-only. **Free tier**: None. **Best for**: merchants wanting AI-powered search and product recommendations that influence cart contents before checkout.

- **[Peak Dynamic Pricing](https://apps.shopify.com/peak-dynamic-pricing)**
  **Rule-based price automation app** for Shopify. Schedules price changes by date/time, adjusts based on demand or inventory, tracks timing impact on sales . **Pricing**: **Ground** free (1 rule), **Basecamp** $1.99/month (5 rules), **Summit** $4.99/month (unlimited), **Everest** $11.99/month (1-minute precision) . **Free tier**: Yes, 1 active rule. **Best for**: merchants wanting automated, time-based price changes without custom development.

- **[Script Editor](https://shopify.dev/docs/apps/checkout)** (**Deprecated**)
  **The Shopify Plus app where Ruby Scripts were written and managed**. With Scripts sunset on June 30, 2026, the Script Editor has no execution path. Shopify directs merchants to **Shopify Functions** (WebAssembly-based, runs server-side) and **Checkout UI Extensions** (sandboxed UI blocks) for equivalent logic . **Pricing**: N/A. **Free tier**: N/A. **Best for**: **historical reference only—do not use for new development**.

## Open-Source GitHub Projects

- **[Open Incentives](https://github.com/squeakycheese/open-incentives)** (source link via author's post)
  **Lightweight, self-hosted, open-source promotion engine** — **the most directly relevant open-source project for checkout discount logic** without enterprise overhead. **Features**: Single-purpose evaluation API (`POST /v1/evaluate` with customer + cart → matched campaigns and discounts); admin portal for creating projects, campaigns, and API keys; demo storefront showing end-to-end integration; runs entirely via `docker compose up` with no SaaS dependency or per-seat pricing . **Tech stack**: Docker, API-first. **Deploy**: Self-hosted (`docker compose up`). **Trade-off**: **Early-stage and intentionally minimal**—no loyalty ledgers, multi-tenant hierarchies, or complex segmentation like Talon.One or Voucherify. It answers one question: "given this customer and this cart, what discount applies?" . **Best for**: developers who want a simple, self-hosted promotion engine they can integrate in an afternoon, without buying an enterprise incentives platform.

- **[Medusa](https://github.com/medusajs/medusa)**
  **Open-source headless commerce platform** (MIT for core) — **a composable commerce framework where checkout is fully yours to customize**. **Features**: Modular architecture with separate modules for cart, payment, fulfillment, and pricing; API-first; developer-friendly TypeScript stack; checkout flow is built by you or via storefront starters. **Tech stack**: Node.js, TypeScript, PostgreSQL. **Deploy**: Self-hosted or Medusa Cloud. **Trade-off**: **Not a checkout customization plugin**—it is a commerce platform where you build the checkout. No pre-built discount engine comparable to Shopify Scripts; you implement pricing and promotion logic in your application layer. **Best for**: developers building custom commerce experiences who want full ownership of checkout logic without platform constraints.

- **[Saleor](https://github.com/saleor/saleor)**
  **Open-source, GraphQL-first headless commerce platform** (BSD-3-Clause) — **a mature composable framework with a rich checkout API**. **Features**: `checkoutCreate`, `checkoutLinesAdd`, `checkoutLinesUpdate` mutations; **custom line price override** (apps with `HANDLE_CHECKOUTS` permission can override variant prices and attach an audit reason) ; shipping method calculation via `deliveryOptionsCalculate`; click & collect support; email and address management. **Tech stack**: Python (Django), GraphQL, PostgreSQL. **Deploy**: Self-hosted or Saleor Cloud. **Trade-off**: **Platform, not a plugin**—checkout logic is implemented via API integrations and apps; no built-in promotion engine comparable to Shopify Scripts. **Best for**: teams wanting a GraphQL-native commerce platform with fine-grained control over checkout pricing and line items.

- **[Spree Commerce](https://github.com/spree/spree)**
  **Open-source eCommerce framework** (AGPL-3.0 for core; dual-licensed for newer versions) — **a battle-tested platform with customizable checkout steps**. **Features**: Modular checkout steps; "over 30 payment provider integrations"; robust discounts system; store credits and gift cards; multi-currency; multi-store support . The **Spree Storefront** (MIT) provides a production-ready Next.js one-page checkout with Stripe/PayPal/Adyen, coupon codes, gift cards, and store credit . **Tech stack**: Ruby on Rails (backend), Next.js (storefront). **Deploy**: Self-hosted (Docker, Kubernetes). **Trade-off**: **Framework, not a drop-in customization tool**—you customize checkout by modifying or extending the platform; no Shopify-style app ecosystem. **Best for**: developers wanting a mature, customizable commerce framework with a modern storefront option.

- **[Vendure](https://github.com/vendure-ecommerce/vendure)**
  **Open-source headless commerce framework** (MIT) — **a TypeScript-first platform with a plugin-based architecture**. **Features**: The **Validate Cart plugin** (`@pinelab/vendure-plugin-validate-cart`) adds custom validation rules before checkout—stock checks, promotion validity, custom strategies via `CartValidatorStrategy` interface; `validateActiveOrder` mutation returns errors and the validated order . **Tech stack**: Node.js, TypeScript, GraphQL, PostgreSQL. **Deploy**: Self-hosted. **Trade-off**: **Platform + plugin ecosystem**—checkout customization is done through plugins and custom strategies, not a visual builder or proprietary scripting language. **Best for**: TypeScript developers wanting a modern commerce framework with extensible cart and checkout validation.

- **[Sylius](https://github.com/Sylius/Sylius)**
  **Open-source eCommerce platform for Symfony** (MIT) — **a PHP-based framework with a dedicated Promotion Bundle**. **Features**: `SyliusPromotionBundle` provides a promotions engine for Symfony commerce applications; decoupled components; API-first architecture . **Tech stack**: PHP (Symfony), Doctrine, MySQL/PostgreSQL. **Deploy**: Self-hosted. **Trade-off**: **Framework, not a checkout customization app**—promotion logic is implemented within the Sylius/Symfony application. No visual rule builder. **Best for**: PHP/Symfony developers wanting an open-source commerce platform with built-in promotion infrastructure.

### Additional Strong Open-Source Options

- **@goobits/store** — Reusable Svelte components for Medusa v2 storefronts (MIT per npm). Includes checkout payment, shipping, review, and confirmation components with Stripe integration and i18n. **Note**: Demo payment forms—**not production-safe**; explicitly warns against handling real card data client-side . **Best for**: Svelte developers wanting Medusa checkout UI components as a starting point.
- **entirius-django-checkout** — Checkout engine for Django (PyPI package). Handles cart lifecycle, order creation, payment intents (PayU, PayPal, Stripe, etc.), discount codes, and per-supplier stock reservation . **Note**: **Django-specific infrastructure**, not a standalone app—requires integration with `django_accounts`, `django_pim`, and related packages. **Best for**: Django developers building multi-channel storefronts who need a checkout engine foundation.

**Frameworks for building custom systems**: Combine **Open Incentives** as a standalone promotion evaluation API with **Medusa**, **Saleor**, or **Vendure** as the commerce platform where you build the checkout, and **Spree Storefront** for a production-ready one-page checkout UI—creating a checkout customization stack. **None of these plug into Shopify's checkout**; Shopify customization requires Shopify Functions and UI Extensions built with Shopify CLI, not open-source tools.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Checkout customization platforms handling pricing, discounts, and payment logic must comply with PCI DSS and data protection regulations (GDPR, CCPA, etc.).
- **The "Shopify checkout customization" vs. "composable commerce platform" distinction is absolute.** **Shopify Scripts, Bold Custom Pricing, Discount Ninja, CartHook, Rebuy, Fast Simon, and Peak** are **apps or platform features for Shopify**—they operate within Shopify's closed checkout environment. **Open Incentives, Medusa, Saleor, Spree, Vendure, and Sylius** are **open-source frameworks or standalone engines**—they require you to own and operate the commerce platform itself. **You cannot use an open-source promotion engine to customize Shopify's checkout**; Shopify's checkout is hosted and sandboxed, and only Shopify Functions and UI Extensions can modify it .
- **Shopify Scripts are dead.** The sunset date was **June 30, 2026** . If you are still running Scripts, your checkout logic has already stopped executing. Migration to Shopify Functions is not optional. **Do not start new development on Scripts or Script Editor.**
- **Open-source checkout customization for Shopify does not exist as a category.** The projects listed are for **composable commerce platforms** where checkout is code you own, or for **standalone promotion engines** you integrate into your own application. **If you are on Shopify, your path is Shopify Functions + UI Extensions, or apps like Bold and Discount Ninja.**
- **Open Incentives is the most directly relevant open-source project** for the core problem of checkout customization—evaluating discount rules against a cart . **The trade-off**: it is early-stage and intentionally minimal. It does not handle shipping rules, payment filtering, or UI customization. It answers one question: what discount applies?
- **Bold Custom Pricing is a pricing app, not a checkout logic engine.** It handles customer-specific and quantity-based pricing . It does **not** replace Scripts for shipping rules, payment filtering, or complex conditional logic. **Discount Ninja and CartHook** address different slices—promotions and post-purchase upsells respectively.
- **Pricing opacity varies.** Bold Custom Pricing publishes tiered pricing ($29–$129/month) ; Peak Dynamic Pricing publishes tiered pricing ($0–$11.99/month) ; Discount Ninja, CartHook, Rebuy, and Fast Simon require sales contact. Shopify Plus starts at $2,300/month. **Validate with direct vendor conversations against your actual checkout complexity and order volume.**
- Self-hosted open-source solutions require proper server setup, security hardening, and ongoing maintenance. **Checkout code handles pricing and payment logic**—ensure your deployment meets PCI DSS requirements and your organization's security standards before processing live transactions.

---

**Made for developers, merchants, and organizations building transparent checkout customization solutions.**
Let's make Checkout Customization more open, data-driven, and merchant-friendly.
