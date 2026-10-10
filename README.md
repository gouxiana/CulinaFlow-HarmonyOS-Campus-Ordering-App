# Campus Takeaway Ordering

A HarmonyOS NEXT campus takeaway ordering app built with ArkTS and ArkUI. The app lets users browse available dining locations, review menus, add items to a cart, confirm packaging preferences, submit orders, and view local order history.

This repository contains the source project and selected project documentation. It does not include personal identity information or school-specific resume material.

## Features

- Account and password input with validation and loading feedback
- Dining-location selection with enabled and coming-soon states
- Menu browsing with category tabs for breakfast, staple food, soup, and stir-fried dishes
- Food cards with quantity controls and cart badge updates
- Cart editing, item deletion, total calculation, and clear-cart confirmation
- Order confirmation with tableware selection and packaging-box quantity
- Local order persistence and order-history browsing
- Pull-to-refresh feedback, end-of-list feedback, and reusable UI components

## Technical Highlights

- HarmonyOS NEXT application structure with an `entry` module
- ArkTS and ArkUI declarative component development
- `@State` and `@Link` for cross-page state synchronization
- Componentized pages for login, restaurant list, restaurant detail, cart, checkout, and order history
- `LazyForEach`-style data-source organization for menu lists
- Local persistence helpers for cart and order data
- Optional network helper examples using HarmonyOS NetworkKit and Remote Communication Kit

## Project Structure

```text
AppScope/                         Application-level resources
entry/src/main/ets/pages/         Main pages and user flows
entry/src/main/ets/components/    Reusable food-item components
entry/src/main/ets/common/        Constants, persistence, and network helpers
entry/src/main/resources/         UI strings, colors, icons, and food assets
docs/                             Sanitized project overview
```

## Run Locally

1. Install DevEco Studio with a compatible HarmonyOS SDK.
2. Open this repository as a HarmonyOS project.
3. Allow DevEco Studio to restore project dependencies.
4. Select a phone, tablet, or compatible emulator target.
5. Build and run the `entry` module.

The project currently uses local mock menu data. Network helper classes are included as optional examples and are not required for the main ordering flow.

## Demo and Documentation

- [Watch the product walkthrough and interaction demo](https://github.com/gouxiana/harmonyos-campus-ordering/releases/tag/v1.0-demo)
- [Read the project overview](docs/project-overview.md)

The Release contains the demonstration video. The source tree intentionally excludes generated build output, IDE caches, dependency folders, and signing-related local configuration.

## Scope and Limitations

This is a front-end interaction prototype. Login, payment, and restaurant data are simulated locally; no production account system or payment service is connected. The project is intended to demonstrate mobile interaction design, state management, local persistence, and HarmonyOS application structure.
