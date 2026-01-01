# Project Context: Attajak (Hugo Site)

## Overview

This is a personal website/blog project built with **Hugo**, a static site generator. It utilizes the **FixIt** theme, specifically managed via the `fixit-bundle` Hugo Module. The site is configured for deployment on **Vercel**.

**Key Technologies:**
*   **Core:** Hugo (Extended version required)
*   **Theme:** FixIt (via Hugo Modules)
*   **Styling:** SCSS (Dart Sass)
*   **Deployment:** Vercel

## Architecture & Structure

*   **`config/_default/`**: Configuration files (TOML format). The main config is split into multiple files (`hugo.toml`, `params.toml`, `menus.toml`, etc.).
*   **`content/`**: Markdown files for the site pages and blog posts.
*   **`assets/`**: Source assets processing pipe. Custom styles are in `assets/css/` (`_custom.scss`, `_override.scss`).
*   **`static/`**: Static files served as-is (images, `robots.txt`, etc.).
*   **`layouts/`**: HTML templates for overriding theme defaults.
*   **`build.sh`**: Custom build script for Vercel that installs specific versions of Hugo, Go, Node.js, and Dart Sass.

## Building and Running

The project uses `npm` scripts for convenience, wrapping standard Hugo commands.

### Prerequisites
*   **Hugo Extended** (>= 0.132.0)
*   **Go** (for Hugo Modules)
*   **Node.js**

### Commands

*   **Install Dependencies:**
    ```bash
    npm install
    ```
    *Note: This might also require `hugo mod get` to fetch theme modules.*

*   **Start Development Server:**
    ```bash
    npm start
    ```
    This runs `hugo server` with flags for development (binding to 0.0.0.0, enabling drafts/future content).

*   **Build for Production:**
    ```bash
    npm run build
    ```
    Or, using the Vercel script (simulates CI environment):
    ```bash
    ./build.sh
    ```

*   **Update Theme Modules:**
    ```bash
    npm run update
    ```

## Development Conventions

*   **Theme Management:** The project uses **Hugo Modules** (`go.mod`, `config/_default/module.toml`). Do not manually clone the theme into `themes/` unless strictly necessary for debugging; rely on `hugo mod` commands.
*   **Configuration:** Adjustments to site settings should happen in `config/_default/`.
*   **Customization:**
    *   **CSS:** Add custom styles to `assets/css/_custom.scss` or `_override.scss`.
    *   **HTML:** Override partials or templates by mirroring the theme structure in `layouts/`.
*   **Content:** New posts are added to `content/posts/`.
