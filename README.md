# Biko User App

Flutter customer app for motorcycle rides and parcel delivery.

```powershell
flutter pub get
flutter test
flutter run --dart-define=SUPABASE_URL=https://your-project.supabase.co --dart-define=SUPABASE_PUBLISHABLE_KEY=your-public-publishable-key
```

Without Supabase values, the app intentionally opens in a disabled setup state.

## Code structure

- `app/`: `user_app`, `user_router`, `user_shell`, and `user_theme`.
- `core/widgets/`: the few widgets shared across features.
- `features/orders/`: order models, rules, service, providers, pages, and widgets.
- `features/maps/`: location picker, route map, place search, and polyline decoding.
- `features/home/`, `features/profile/`, and `features/notifications/`: small focused features with direct file names.

Keep trusted order, pricing, and authorization rules in the existing PostgreSQL RPCs; the User App only validates input, presents state, and invokes those contracts.


## Independent repository

Run all commands above from this repository root. `packages/app_core` is a local
copy owned by this repository: no sibling checkout or Git package is required.
Changes to this copy do not propagate to the other mobile app automatically.

The shared Supabase backend (migrations, Edge Functions, seed data, database tests)
is maintained in https://github.com/ibrahimmaher2503-source/biko-dashboard.
Use the same backend URL and public key for the customer, driver, and dashboard.
Backend contract changes must remain compatible with both released mobile apps.
CI is not configured for this extracted mobile repository.

## Extraction provenance

Extracted from https://github.com/ibrahimmaher2503-source/biko at `eb44e7c36d528059ece11d0cb5fca1633dfd8ad9`.
This repository starts with a snapshot commit. Earlier commit history remains
in the original repository, which was left intact.
