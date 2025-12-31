# Professional JSON Formatter + Diff Tool

A high-performance, single-file web application for formatting, validating, and comparing JSON data. Built with vanilla HTML, CSS, and JavaScript, it provides a private, client-side, dependency-free environment.

## Features

### Editor & UI
- **Side-by-Side Comparison**: Dual panes with synchronized scrolling for efficient visual auditing.
- **Real-Time Syntax Highlighting**: A custom, character-by-character tokenizer (regex-free) provides instant feedback with zero latency.
- **Dynamic Line Numbering**: Accurate line counts that remain correct across formatting, minification, and diff alignment.
- **Per-Pane History**: Local Undo (**⟲**) and Redo (**⟳**) track manual edits and actions (Format, Minify, Clear). *Note: History is session-based and does not persist across refreshes.*

### JSON Toolkit
- **Formatting & Minification**: 2-space pretty printing and compact minification for production storage.
- **Strict Validation**: Precise line and column error reporting. Per RFC 8259 and `JSON.parse` strictness, comments, single quotes, and trailing commas are invalid.
- **Semantic Normalization**: Recursively sorts object keys before diffing so comparisons focus on values rather than key order.

### Diff Engine
- **Horizontal Row Alignment**: Placeholder lines keep corresponding JSON structures aligned across both panes.
- **Dual-Algorithm Logic**:
  - **LCS (Longest Common Subsequence)**: Precision diffing (up to 2,000 lines) that maximizes unchanged lines for readability.
  - **Heuristic Fallback**: Automatically switches for large inputs to keep the UI responsive.
- **Summary Bar**: Real-time statistics for added (+), removed (-), and changed (!) lines.

### Productivity & Persistence
- **Global Controls**: Pane swapping, sample data loading, and a system-aware Light/Dark theme toggle.
- **Unified Diff Report**: Downloadable .txt report with timestamp, statistics, and algorithm metadata. Copy uses your browser clipboard (navigator.clipboard.writeText) and happens locally (no upload).
- **Persistence**: Automatically saves contents and settings to localStorage (scoped to the origin and saved across browser sessions). Privacy note: use Clear Pane to remove stored content.

## Quick Start
No installation required. Open `index.html` in any modern web browser.

## Keyboard Shortcuts
| Action | Shortcut |
| :--- | :--- |
| **Undo** | `Ctrl/Cmd + Z` |
| **Redo** | `Ctrl/Cmd + Shift + Z` (or `Ctrl + Y`) |
| **Format JSON** | `Ctrl/Cmd + Enter` |
| **Run Diff** | `Ctrl/Cmd + D` |
| **Clear Pane** | `Ctrl/Cmd + L` |

## Performance & Limitations
- **File Size**: Speed-optimized; however, files >5MB may cause brief latency during diff calculation.
- **Strict Grammar**: Validation fails on non-standard JSON, ensuring compatibility with production services.

## Roadmap
- Drag-and-drop file loading.
- In-editor search and filtering.
- Collapsible JSON nodes.

## Screenshots
![Interface Demo](https://github.com/user-attachments/assets/c8574345-387f-4d96-824d-63eda0a0a2fe)
![Diff Alignment](https://github.com/user-attachments/assets/5e36a52e-c50f-4699-a2ec-f70c3e864ddd)

## License

MIT License. Free for personal and commercial use.
