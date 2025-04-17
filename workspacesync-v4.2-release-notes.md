
# WorkspaceSync v4.2 – Release Notes & Changelog

---

## 🛠️ Developer-Facing Changelog

**Release Version:** v4.2  
**Release Date:** April 15, 2025  
**Maintainer:** Engineering Team, WorkspaceSync

### 🚀 New Features
- **Real-time Sync Enhancements:** Upgraded socket infrastructure for faster updates across distributed environments.
- **Modular Authentication:** Introduced plug-and-play auth adapters for Google, Microsoft, and custom SSO providers.

### 🔧 Improvements
- Refactored directory traversal logic to reduce sync time by 23% on large filesystems.
- Improved webhook response times and reduced average API latency by 15%.

### 🐞 Bug Fixes
- Fixed issue where nested folders failed to reflect changes if source was renamed mid-sync.
- Patched edge case where OAuth token refreshes were inconsistently handled on slow networks.
- Corrected timezone offset error in audit log timestamps.

### 🧪 Developer Notes
- Deprecated `syncProfileLegacy()` method. Use `initSyncProfile()` instead.
- Added support for environment variables in Docker deployment (`WSYNC_AUTH_MODE`, `WSYNC_VERBOSE_LOGGING`).

---

## 📢 User-Facing Release Notes

**What’s New in WorkspaceSync v4.2?**

### 🔄 Smoother Syncing Experience
You’ll now notice faster syncing between your folders, even for large files. This update brings behind-the-scenes improvements that keep everything running more reliably across teams.

### 🔐 Easier Sign-In
We now support sign-in with Microsoft and Google accounts — no need to remember another password.

### 🧘 Fewer Glitches
- Files no longer disappear or get stuck when folders are renamed.
- All timestamps now match your local time, so no more confusion in logs.

### 📌 Coming Soon
We’re working on a new Activity Dashboard that gives you insights into sync performance across your organization. Stay tuned for updates!

---

For any questions, feedback, or to report a bug, contact support@workspacesync.com.
