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

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global e-commerce checkout and shopping cart software market is valued at approximately **$10B to $13B** (with the broader e-commerce personalization and promotion layer adding another **$8B+**), expanding at a CAGR of ~14%–19%. The sector exhibits **two-tier market dynamics**: the underlying platform layer is highly concentrated around major platforms (e.g., Shopify dominating SMB and mid-market hosted checkout), while the ecosystem of checkout customization, promotion engines, and upsell apps remains **moderately to highly fragmented**, with hundreds of specialized SaaS solutions competing alongside emerging open-source composable commerce frameworks.

## SaaS/Hosted Platforms

| Platform / App | Company Size (Revenue / Valuation) | Pricing (Starting Tier) | Free Tier / Free Trial Limits | Description & Key Strengths |
|---|---|---|---|---|
| **[Shopify Scripts & Script Editor](https://shopify.dev/docs/apps/checkout)** | ~$11.6B Revenue / ~$210B+ Market Cap | From **$2,300/mo** (included with Shopify Plus) | **No free tier or trial** (Requires active Shopify Plus subscription; Scripts stopped execution June 30, 2026, migrating to Shopify Functions) | Legacy Ruby-based checkout logic engine for Shopify Plus allowing line item, shipping, and payment customization. **Deprecated / Sunsetting June 30, 2026**; stores must migrate to WebAssembly Shopify Functions. |
| **[Bold Custom Pricing](https://www.boldcommerce.com/)** | ~$25M–$30M ARR / $44M VC Funded | From **$29/mo** (Essential plan; $69/mo Standard, $129/mo Complete) | **14-day free trial** (Full feature access to test wholesale/VIP tagging and quantity break discounts) | Customer-specific and quantity-based pricing app for Shopify. Uses customer tags to assign wholesale, VIP, or tiered group pricing without custom code. |
| **[Rebuy Engine](https://rebuyengine.com/)** | ~$12M–$19M ARR / $21.4M VC Funded | From **$25/mo** (Build Your Own / a la carte packages; Full suite from $534/mo) | **14-day free trial**; also offers **Rebuy Monetize free tier** (Free post-purchase offers earning transaction revenue, dev store access) | AI-powered personalization, Smart Cart, and upsell engine with Smart Links and checkout extensions to dynamically adjust cart line items. |
| **[Fast Simon](https://www.fastsimon.com/)** | ~$5M–$15M ARR (Private) | From **$39.99/mo** (Starter plan; Essential plan at $99.99/mo) | **Free tier available** (up to 100 monthly sessions, includes AI instant search & filters); **14-day free trial** on paid tiers | Search, merchandising, and product personalization SDK/app providing AI-driven search, recommendations, and cart-intent customization before checkout. |
| **[CartHook](https://carthook.com/)** | Processed $1B+ GMV (Acquired by Pantastic / Shop Circle) | **$0/mo base** on Pay As You Go ($0.12/order after free tier + 1% rev share) or **$49/mo** (Growth plan) | **Free tier: 20 orders/mo** on Pay As You Go plan ($0/mo base fee); **14-day free trial** on Growth ($49/mo) and Scale ($149/mo) plans | Post-purchase upsell and cross-sell platform with drag-and-drop funnel builder, checkout extensions, and one-click upsell acceptance. |
| **[Discount Ninja](https://apps.shopify.com/discount-url)** | ~$300K–$1M ARR (Ninja Commerce / Limoni Apps) | From **$49/mo** (Starter plan, up to 500 orders/mo; Pro $99/mo, Grow $199/mo) | **14-day free trial** (Includes full access to discount stacking, gifts, and promotion rules across all subscription plans) | Advanced promotion engine for Shopify with automated gifts, complex discount stacking, and dynamic promotion rule combinations. |
| **[Peak Dynamic Pricing](https://apps.shopify.com/peak-dynamic-pricing)** | Bootstrapped / Micro-SaaS (Pricing.AI) | From **$1.99/mo** (Basecamp plan; Summit $4.99/mo, Everest $11.99/mo) | **Free forever plan: Ground** (Free with 1 active pricing rule); **14-day free trial** on paid tiers | Rule-based and time-based price automation app for Shopify that schedules scheduled and demand-based price changes. |

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
