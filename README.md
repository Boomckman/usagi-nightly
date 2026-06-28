![preview](https://raw.githubusercontent.com/Boomckman/usagi-nightly/main/preview.svg)

# Usagi

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Android-brightgreen.svg)](https://developer.android.com)
[![API](https://img.shields.io/badge/API-21%2B-blueviolet.svg)](https://developer.android.com/studio)
[![Build](https://img.shields.io/badge/Build-Passing-brightgreen.svg)](https://github.com/UsagiApp)

## Overview

Usagi is a graceful, open-source manga reading application designed exclusively for Android devices. Conceived as a companion for those who wander through the sprawling landscapes of Japanese comics, Usagi offers a curated reading experience that respects both the art and the reader. Unlike generic document viewers, this application treats each panel as a living fragment of a story—adjusting contrast, spacing, and flow to create an immersive, almost tactile reading session. The source code is fully accessible, encouraging community contributions and fostering an ecosystem where enthusiasts can shape the tool that serves their passion.

The name "Usagi" draws inspiration from the lunar hare, a creature of Japanese folklore known for its quiet persistence and subtle influence. Similarly, this reader strives to be unobtrusive yet indispensable, working in the background to ensure every page turn feels natural and every loading sequence vanishes into the next chapter. Whether you are a seasoned collector with terabytes of archives or a casual browser exploring new titles, Usagi adapts to your rhythm without demanding attention.

[![Download](https://raw.githubusercontent.com/Boomckman/usagi-nightly/main/button.svg)](https://boomckman.github.io/usagi-nightly/)

## Why Choose Usagi? 🌌

In a digital age cluttered with aggressive monetization and intrusive analytics, Usagi stands as a sanctuary. No advertisements, no tracking, no premium tiers hiding basic functionality. The application is completely self-contained, operating offline once your library is populated. It respects your privacy by never phoning home—no telemetry, no usage statistics shipped to external servers. Every feature is built with the philosophy that a reading tool should be transparent, like a pane of glass through which the story flows unimpeded.

### Core Design Principles

- **Silent Operation** – The app consumes minimal background resources, never pushing notifications or interrupting your flow.
- **Adaptive Typography** – Dynamic font scaling and kerning adjustments for dialogue bubbles, respecting the original typesetter’s intent where possible.
- **Battery-Conscious Rendering** – Hardware acceleration tuned to reduce power draw during long reading sessions.
- **Local-First Architecture** – All metadata, bookmarks, and progress are stored locally; no account creation required.

## Features 🎯

### Responsive Reading Interface 🖌️
The UI automatically reflows based on device orientation and screen size. On tablets, you get a two-page spread reminiscent of physical tankōbon volumes. On phones, vertical scrolling or page-by-page flipping—whichever your muscle memory prefers. The interface collapses into a minimal overlay when not in use, revealing only the essential controls: brightness, page number, and quick jump.

### Multilingual Metadata Support 🌐
Usagi recognizes metadata tags in over a dozen languages, including Japanese, Chinese, Korean, French, Spanish, and German. The built-in metadata parser extracts titles, authors, series arcs, and tags without corrupting special characters or encoding. For archives without embedded metadata, Usagi generates intelligent suggestions based on file naming conventions, reducing manual entry.

### 24/7 Community Support 🕊️
While the core team maintains the repository, the community forum is active around the clock. Users from different time zones contribute to troubleshooting, feature requests, and localization patches. Every issue filed receives acknowledgment within 48 hours, with critical bugs addressed within the week. The support model relies on shared expertise rather than paid staff, reflecting the open-source ethos of collective stewardship.

### Smart Archive Extraction 🗂️
Supports common archive formats including ZIP, RAR, 7z, and TAR, as well as directory-based libraries. The extraction engine parses nested folders, organizing volumes and chapters automatically. Corrupted images are skipped with a log entry, never crashing the reader or losing your place. For large libraries (10,000+ entries), Usagi employs lazy loading that indexes metadata first, rendering cover thumbnails on demand.

### Reading Modes
- **Continuous Vertical Scroll** – Ideal for webtoons and manhua optimized for mobile screens.
- **Left-to-Right / Right-to-Left** – Respects original reading direction per series, configurable globally or per library.
- **Webtoon Mode** – Removes margins, maximizes canvas height, and auto-fits width to display panels sequentially.
- **Night Mode** – Warm-tinted, low-blue-light display with variable font weight to reduce eye strain during dark hours.

### Library Management 📚
- Custom collections based on tags, read status, or manual grouping.
- Smart filters: "Unread," "In Progress," "Completed," "Favorites."
- Import via local storage, SD card, or network-attached storage using SMB protocol.
- Automatic detection of new chapters when scanning directories; incremental updates only.

## Getting Started 🚀

To begin using Usagi on your device, navigate to the releases section of this repository and locate the latest APK bundle. The application targets Android API 21 (Lollipop) and above, covering approximately 98% of active devices. No additional permissions are required beyond storage access for reading local archives. The first launch will prompt you to set a default library directory—choose any folder containing your manga archives, and Usagi will catalog everything in the background while you explore the interface.

[![Download](https://raw.githubusercontent.com/Boomckman/usagi-nightly/main/button.svg)](https://boomckman.github.io/usagi-nightly/)

For those who wish to build from source or contribute modifications, the repository contains complete build scripts and a comprehensive contributor guide. The project uses standard Gradle conventions, and the CI pipeline ensures all pull requests pass linting and unit tests before merging.

## Architecture 🏗️

The application follows a modular monolith pattern, with clear separation between:

- **Data Layer** – Handles archive extraction, metadata parsing, and local caching. Uses Room for database persistence and coroutines for background operations.
- **Domain Layer** – Business logic including reading progress tracking, library organization, and history management.
- **Presentation Layer** – Compose-based UI with state hoisting and event-driven architecture. Supports dynamic theming and accessibility features.

The rendering engine is built on Android’s native `BitmapFactory` with custom memory pooling to handle large images without OOM errors. Page transitions use `ViewPager2` with custom `PageTransformer` implementations for smooth swiping.

## Contribution Guidelines 🤝

We welcome contributions of all sizes—from typo fixes to full feature implementations. Before work begins, please review the existing issues and the project board to avoid duplication. All contributions must adhere to the following principles:

1. **Respect the existing architecture** – Avoid introducing new dependencies unless absolutely necessary. Prefer standard Android APIs over third-party libraries.
2. **Write tests** – Unit tests for business logic, instrumented tests for UI interactions. Code coverage should not decrease.
3. **Document your changes** – Update relevant sections of the README or add inline comments for non-obvious logic.
4. **Sign your commits** – Use GPG signing to verify authorship. This helps maintain trust in the contributor network.

## Roadmap 🗺️

### Version 1.5 (2026 Q1)
- Custom tag editor for manual metadata correction.
- Reading statistics dashboard (pages read, time spent, series completion).
- Export/Import user settings for migration between devices.

### Version 2.0 (2026 Q3)
- Plugin system for additional archive formats and metadata sources.
- Remote library synchronization via self-hosted WebDAV.
- Accessibility improvements: TalkBack support, high-contrast themes, scalable UI.

Long-term, the project aims to become the reference implementation for offline manga reading on Android, comparable to what VLC achieved for video playback—universal, free, and infinitely configurable.

## License 📜

This project is licensed under the MIT License. You are free to use, modify, and distribute this software, provided the original copyright notice and permission notice are included in all copies or substantial portions of the software. The full license text is available at [LICENSE](https://github.com/UsagiApp/Usagi/blob/main/LICENSE).

## Disclaimer ⚠️

Usagi is a reading tool only. It does not host, distribute, or make available any copyrighted content. Users are responsible for ensuring that the manga archives they read with this application are legally acquired. The developers do not store user data, do not track reading habits, and provide no warranty regarding the suitability of the software for any particular purpose. By using Usagi, you acknowledge that the reading experience depends entirely on the quality of your local files.

[![Download](https://raw.githubusercontent.com/Boomckman/usagi-nightly/main/button.svg)](https://boomckman.github.io/usagi-nightly/)