# Attajak Hugo Blog

## Overview
This is a Hugo static site generator project using the FixIt theme with multiple component modules. The site is a personal blog/portfolio for Attajak with posts, projects showcase, and social links.

**Current State**: Successfully configured and running on Replit with all themes installed and server running on port 5000.

## Recent Changes (October 28, 2025)
- Installed Hugo v0.147.3+extended via Nix package manager
- Manually cloned all required theme submodules (FixIt and 10 component themes)
- Updated package.json server script to run on port 5000 with proper host binding
- Configured workflow to run Hugo development server
- Set up deployment configuration for production builds
- Site is fully functional and accessible

## Project Architecture

### Technology Stack
- **Static Site Generator**: Hugo v0.147.3 (extended)
- **Theme**: FixIt v0.4.0-alpha.2
- **Package Manager**: npm (for scripts only)
- **Deployment**: Replit Autoscale (static site serving)

### Directory Structure
```
/
├── archetypes/          # Content templates
├── assets/              # CSS, JS, images
├── config/_default/     # Hugo configuration files
│   ├── hugo.toml       # Main Hugo config
│   ├── params.toml     # Theme parameters
│   └── ...             # Other config files
├── content/             # Markdown content
│   ├── posts/          # Blog posts
│   ├── projects/       # Projects showcase
│   └── ...
├── data/                # Data files (YAML)
├── layouts/             # Custom layouts/templates
├── static/              # Static files
│   └── favicon/        # Site icons
├── themes/              # Hugo themes (Git cloned)
│   ├── FixIt/          # Main theme
│   └── ...             # Component themes
└── package.json         # NPM scripts
```

### Hugo Themes/Components
The site uses the following themes via Hugo's theme composition:
1. **FixIt** - Main theme
2. **cmpt-flyfish** - Fish swimming animation
3. **cmpt-mdevtools** - Mobile dev tools (eruda)
4. **cmpt-translate** - Automatic translation
5. **component-projects** - GitHub projects display
6. **hugo-atom-feed** - ATOM feed support
7. **hugo-json-feed** - JSON feed support
8. **shortcode-asciinema** - Asciinema embed
9. **shortcode-caniuse** - Can I Use embed
10. **shortcode-docs-bookmark** - FixIt docs bookmarks
11. **shortcode-mmt-netease** - NetEase Cloud music comments
12. **shortcode-rewards** - Reward/sponsor logs

### Key Configuration

#### Server Configuration
- **Development Port**: 5000
- **Host Binding**: 0.0.0.0 (required for Replit)
- **Base URL**: Configured for attajak.vercel.app (production)
- **Live Reload**: Enabled in development

#### NPM Scripts
- `npm run server` - Start Hugo development server on port 5000
- `npm run build` - Build production site
- `npm run create` - Create new content

#### Deployment
- **Type**: Autoscale (static site)
- **Build Command**: `hugo --gc --minify --logLevel info`
- **Run Command**: Hugo server in production mode on port 5000

### Site Features
- Blog posts with markdown support
- Projects showcase (GitHub integration)
- Search functionality (Fuse.js)
- RSS/Atom/JSON feeds
- Social media links
- Responsive design
- Dark/light theme toggle
- PWA support (disabled in development)

## Development Notes

### Important Considerations
1. **Git Submodules**: Themes are cloned manually since git submodule commands are restricted
2. **Hugo Version**: Using v0.147.3 (theme requires 0.147.7, but works with minor warning)
3. **Port Configuration**: Must use port 5000 for Replit frontend visibility
4. **Host Binding**: 0.0.0.0 is required for Replit's proxy/iframe setup

### Known Warnings
- Minor version compatibility warning with FixIt theme (requires Hugo 0.147.7, have 0.147.3)
- Development environment disables: comment system, PWA, CDN, fingerprint, analytics

### Content Management
- Blog posts are in `content/posts/` directory
- Projects are auto-generated from GitHub via component-projects
- Static assets go in `static/` directory
- Custom CSS/JS in `assets/` directory

## Replit Environment

### Installed Packages
- Hugo (via Nix system package)

### Workflows
- **Server**: Runs `npm run server` on port 5000 (webview output)

### Deployment Ready
The site is configured for deployment with proper build and run commands. When ready to publish, use Replit's deployment feature.
