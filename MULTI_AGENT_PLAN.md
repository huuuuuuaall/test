# Mono - Project Implementation Plan

## 1. Project Overview
**App Name:** Mono
**Platform:** Android (via Flutter)
**Target Store:** RuStore
**Tech Stack:** Flutter, Firebase, SQLite (local cache), WebRTC (calls)
**Design System:** Material 3, Custom Monochrome Theme with user selection.

## 2. Architecture & Tech Stack
- **State Management:** Flutter Bloc (Production standard for complex apps)
- **Navigation:** go_router
- **Dependency Injection:** get_it + injectable
- **Local Database:** Drift (SQLite abstraction) or Hive for fast caching
- **Backend:** Firebase (Auth, Firestore, Storage, Functions) + WebRTC signaling server (if needed, or Firestore for signaling)
- **Encryption:** libsodium / pointycastle for E2EE

## 3. Module Structure (lib/)
- `core/` (Utils, Constants, Theme, Extensions, Network Clients)
- `features/`
  - `auth/` (Login, Register, Phone/Email verification)
  - `profile/` (View, Edit, Music, Status, Avatar)
  - `contacts/` (Local device contacts sync, filtering)
  - `chat/` (List, Detail, Media, Voice, Stickers, E2EE logic)
  - `calls/` (Audio/Video, PiP service, WebRTC)
  - `channels/` (Broadcasts, Comments)
  - `wallet/` ("Lightning" currency, Transactions)
  - `store/` (Username marketplace)
  - `settings/` (Theme, Security, Privacy)

## 4. Phase 1: Foundation (Current Focus)
- Initialize Flutter Project
- Setup Linter (flutter_lints) and Static Analysis
- Setup Navigation (go_router)
- Configure Theming (Light/Dark + Monochrome default)
- Implement Splash Screen

## 5. Detailed Roadmap (Based on User 17 Stages)
1.  **Basic Setup:** Project init, Navigation, Splash.
2.  **Auth:** Firebase Auth (Email/Pass), Error handling.
3.  **Profile:** Firestore sync, Local cache, Media upload.
4.  **Chat List:** Real-time updates, Local storage (Offline first).
5.  **Messaging:** Text, SQLite cache, Statuses, Drafts.
6.  **Notifications:** FCM, Background handling, Deep links.
7.  **Media:** Compress, Upload, Download, Gallery permissions.
8.  **Security:** Local Auth (Bio/Pin), Screen protection.
9.  **E2EE:** Local Key generation, Signal Protocol implementation (concept).
10. **Groups/Channels:** Role management, Read-only modes.
11. **Stickers:** Lottie animations, Packs management.
12. **Calls:** Agora or pure WebRTC, Foreground services.
13. **Wallet:** Internal currency logic, Atomic transactions.
14. **Username Market:** Auction/Sale logic.
15. **Settings:** Granular control.
16. **Polish:** UI/UX refinement, Performance profiling.
17. **Release:** ProGuard, Signing, APK generation.

## 6. Specific Requirements Integration
- **Contacts:** `flutter_contacts` integration to fetch device contacts and match with DB.
- **Video Messages:** Camera recording circular view.
- **Animated Emojis:** Lottie or Rive integration.
- **Russian Language:** Default locale `ru`.
