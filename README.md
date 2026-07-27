# Hearts Turn Healing & Recovery Website

Eleventy-powered static website for Hearts Turn Healing & Recovery.

This site is built with [Eleventy](https://www.11ty.dev/) and deployed through Netlify. The project was migrated from an older Jekyll site.

## Tech Stack

* **Static site generator:** Eleventy (11ty)
* **Templates:** Nunjucks (`.njk`)
* **Styling:** Pico CSS + custom CSS
* **Hosting:** Netlify
* **Forms:** Netlify Forms
* **Source control:** Git / GitHub

## Requirements

Before working on the site, install:

* Node.js
* npm
* Git

Check versions:

```bash
node --version
npm --version
git --version
```

## Getting Started

Clone the repository:

```bash
git clone <repository-url>
cd hrts-trn
```

Install dependencies:

```bash
npm install
```

## Local Development

Start the Eleventy development server:

```bash
npm run start
```

The site will build and become available at:

```
http://localhost:8080
```

Eleventy will watch files and rebuild automatically while editing.

## Production Build

To generate the production site:

```bash
npm run build
```

The generated site will be placed in:

```
_site/
```

The `_site` directory is not committed to Git. Netlify generates it during deployment.

## Project Structure

```
.
├── src/
│   ├── _data/
│   │   └── site.json        # Site-wide information
│   │
│   ├── _includes/
│   │   └── layouts/
│   │       └── base.njk     # Main page layout
│   │
│   ├── css/
│   │   └── style.css        # Custom styles
│   │
│   ├── images/              # Images copied directly to output
│   │
│   ├── index.njk            # Homepage
│   ├── about.njk            # About page
│   ├── contact.njk          # Contact page
│   └── faq.njk              # FAQ page
│
├── .eleventy.js             # Eleventy configuration
├── netlify.toml             # Netlify deployment settings
├── package.json             # npm scripts and dependencies
└── README.md
```

## Adding a New Page

Create a new `.njk` file in `src/`.

Example:

```yaml
---
layout: layouts/base.njk
title: New Page

eleventyNavigation:
  key: New Page
  title: New Page
  order: 5
---
```

Add page content below the front matter.

The navigation menu will automatically update.

## Editing Site Information

Update:

```
src/_data/site.json
```

This contains reusable information such as:

* Site title
* Description
* Contact information
* Footer text

## Images

Place images in:

```
src/images/
```

They will be copied automatically during builds.

Reference them:

```html
<img src="/images/example.jpg" alt="Description">
```

## Forms

Forms use Netlify Forms.

After deploying:

1. Open the Netlify dashboard
2. Go to **Forms**
3. Confirm the form has been detected

If a new form is added, it must exist in the generated HTML during deployment for Netlify to detect it.

## Deployment

Netlify builds the site automatically from Git.

Build settings:

```
Build command:
npm run build

Publish directory:
_site
```

## Common Maintenance Commands

Install new packages:

```bash
npm install package-name
```

Check dependencies:

```bash
npm audit
```

Clean generated files:

```bash
rm -rf _site
```

Rebuild:

```bash
npm run build
```

## Eleventy Notes

This project uses Nunjucks templates.

Avoid Jekyll/Liquid syntax such as:

```liquid
{{ value | default: "text" }}
```

Use Nunjucks instead:

```njk
{% if value %}
{{ value }}
{% else %}
text
{% endif %}
```

## Future Improvements

Potential improvements:

* Add optimized image handling with Eleventy Image
* Add SEO metadata
* Add Open Graph/social sharing images
* Improve mobile navigation
* Add analytics if desired
* Add privacy policy and accessibility review
