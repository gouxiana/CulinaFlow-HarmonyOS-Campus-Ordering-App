# Project Overview

## Product Concept

The app is a campus takeaway ordering experience designed to reduce queueing during busy meal periods. Users can browse dining locations, select food, adjust quantities, confirm packaging preferences, submit an order, and review previous orders in one continuous flow.

## User Flow

```text
Login
  -> Restaurant list
  -> Menu categories
  -> Food details and cart
  -> Order confirmation
  -> Local order history
```

## Page Responsibilities

| Page | Responsibility |
| --- | --- |
| `Index.ets` | Login state, input validation, loading feedback, and page routing |
| `RestaurantListPage.ets` | Restaurant selection, unavailable-state messaging, logout, and order-history entry |
| `RestaurantDetailPage.ets` | Category tabs, menu rendering, quantity changes, refresh feedback, and cart entry |
| `ShoppingCartPage.ets` | Cart editing, deletion, total calculation, and checkout entry |
| `OrderConfirmPage.ets` | Order review, tableware choice, packaging-box quantity, and submission |
| `OrderHistoryPage.ets` | Local order retrieval and order-card rendering |

## Implementation Notes

- `@State` stores page-local interactive state such as account input, menu category, cart contents, totals, and loading status.
- `@Link` synchronizes page transitions and shared cart state between parent and child components.
- Food items are represented as typed data objects with identifiers, names, categories, prices, and descriptions.
- Cart totals and quantities are recalculated after every add, remove, or quantity-change action.
- Order records are serialized to local storage so the history page can restore them after navigation.
- Touch and scroll events provide pull-to-refresh and end-of-list feedback without relying on a backend service.

## Design Decisions

- The primary ordering path is kept linear so users can reach checkout with minimal navigation.
- Disabled restaurant buttons communicate future scope without presenting dead-end interactions.
- Cart count and total price are updated immediately to make selection feedback visible.
- Tableware and packaging choices are confirmed before submission so the final order state is explicit.

## Known Boundaries

- Login and payment are mock interactions.
- Restaurant and menu data are local sample data.
- Network helper examples are separated from the main local-data flow.
- A production version would add authentication, inventory, order-status updates, and payment integration.
