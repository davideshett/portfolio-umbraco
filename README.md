# David Eshett — Portfolio

Personal portfolio site built with Umbraco 13 and .NET 8. Demonstrates Block Grid content modeling, composable Element Types, and clean Razor rendering.

> 🚧 Work in progress — built in public as I learn Umbraco. See [Project Status](#project-status) below.

---

## About this project

This repo is my developer portfolio, but it's also a deliberate learning project. Rather than building the fastest possible static site, I'm using it as an excuse to go deep on Umbraco 13 — modeling content the way a real editorial team would, using Block Grid for flexible layouts, and keeping the frontend clean and framework-free.

The design is brutalist-minimal: heavy typography, grayscale imagery, sharp geometry, no rounded corners. The tech stack is deliberately boring — no Tailwind, no JS framework, no build step beyond `dotnet build`. Just Umbraco, Razor, and handwritten CSS.

## Tech stack

- **CMS** — Umbraco 13 LTS
- **Runtime** — .NET 8
- **Database** — SQLite (local dev), SQL Server (planned for production)
- **Rendering** — Razor views with ModelsBuilder (embedded mode)
- **Frontend** — Vanilla HTML and CSS, Inter font, Material Symbols icons
- **Editor** — Block Grid for page composition

## Features

- **Flexible page layouts** via Block Grid — editors can add, reorder, resize, and remove content blocks without touching code
- **Composable content model** with six reusable Element Types (Hero, Logo Strip, Section Heading, Expertise Card, Project Card, CTA)
- **Responsive design** — single-column on mobile, multi-column grids on desktop, CSS variables for theming
- **SEO-ready** — page-level title and meta description fields on every page

## Project status

| Page | Status |
|---|---|
| Home | 🚧 Backoffice complete, frontend rendering in progress |
| Resume | 📋 Planned |
| Blog (listing + detail) | 📋 Planned |
| Contact (with form) | 📋 Planned |

## Getting started

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- A code editor — Visual Studio 2022, Rider, or VS Code

### Run locally

```bash
# Clone
git clone https://github.com/davideshett/portfolio-umbraco.git
cd portfolio-umbraco/DavidEshett.Portfolio

# Restore and run
dotnet restore
dotnet run
```

On first run, Umbraco's installer wizard will open in your browser. Pick **SQLite** as the database, create an admin account, and you're in.

The site runs at `https://localhost:44xxx` (check the terminal for the exact port). The backoffice is at `/umbraco`.

### Project structure

```
DavidEshett.Portfolio/
├── Views/
│   ├── _Layout.cshtml           # Master layout (shared chrome)
│   ├── HomePage.cshtml          # Home page template
│   └── Partials/
│       └── blockgrid/
│           └── Components/      # One partial per Element Type
├── wwwroot/
│   ├── css/styles.css           # Handwritten CSS, CSS variables
│   └── images/                  # Static assets
└── umbraco/                     # Umbraco runtime files (gitignored db)
```

## What I'm learning

Each page of the portfolio is built around a specific Umbraco concept, documented as I go:

1. **Home page** — Block Grid, Element Types, master layouts
2. **Resume page** — Document Type compositions, nested block structures
3. **Blog** — content trees, listing pages, detail routing, pagination
4. **Contact** — SurfaceControllers, forms, email sending

Each stage has its own writeup in the `/docs` folder (or will, as the project progresses).

## License

MIT — feel free to use the structure and code as a starting point for your own Umbraco learning.

## Credits

- Design inspired by editorial and brutalist web design traditions
- Built while learning from the [Umbraco 13 docs](https://docs.umbraco.com/umbraco-cms/13.latest) and Umbraco community writeups
- Portrait and project imagery are placeholders — all code is my own
