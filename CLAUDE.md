# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for Chris Networks, a local IT services company in Almere specializing in workplace management (werkplekbeheer). The site is optimized for local SEO and lead generation.

## Commands

### Development
```bash
# Open the website locally (no build process needed)
open index.html

# Deploy to Vercel (automatic on git push)
git push origin main

# Test PHP API locally (requires PHP installed)
php -S localhost:8000
```

### Common Tasks
```bash
# Validate HTML
# Use online validator: https://validator.w3.org/

# Check for broken links
# Manual check or use online tools

# Update sitemap after adding pages
# Manually edit sitemap.xml
```

## Architecture

### Tech Stack
- **Frontend**: Static HTML, CSS (with CSS custom properties), Vanilla JavaScript
- **Backend**: PHP serverless functions on Vercel
- **Deployment**: Vercel with automatic deployments
- **Analytics**: Google Analytics (G-M8QSY1HVGL)

### Project Structure
```
/
├── index.html                    # Main landing page
├── wat-is-werkplekbeheer.html   # Service explanation page
├── voordelen-werkplekbeheer.html # Benefits page
├── werkwijze.html               # Work methodology page
├── kosten-werkplekbeheer.html   # Pricing page
├── api/
│   └── index.php               # Contact form handler (placeholder)
├── vercel.json                 # Vercel configuration
├── sitemap.xml                 # SEO sitemap
└── robots.txt                  # Search engine rules
```

### Key Design Patterns

1. **SEO-First Architecture**: Every page is optimized for local search with Schema.org structured data, targeting "werkplekbeheer Almere" keywords.

2. **Performance Optimization**: 
   - Critical CSS inlined in HTML
   - Font preloading with fallback strategies
   - Mobile-first responsive design
   - Conditional animation disabling on mobile

3. **Lead Generation Focus**: Multiple contact forms and CTAs throughout, with pricing calculator for engagement.

### Development Guidelines

#### Adding New Pages
1. Create new HTML file following existing naming convention (kebab-case)
2. Add URL rewrite in `vercel.json` for clean URLs
3. Update `sitemap.xml` with new page
4. Include consistent header/footer structure
5. Add appropriate Schema.org markup

#### Modifying Styles
- CSS variables are defined in `:root` selector in each HTML file
- Maintain mobile-first approach with media queries
- Test on mobile devices for performance

#### API Development
The `api/index.php` file is a placeholder. When implementing:
- Use proper input validation and sanitization
- Add CORS headers if needed
- Implement rate limiting for contact forms
- Send emails via a service like SendGrid or Postmark

#### SEO Considerations
- Target keywords: "werkplekbeheer Almere", "IT-beheer Almere", "digitale werkplekken"
- Maintain local business Schema.org markup
- Keep meta descriptions unique and under 160 characters
- Use semantic HTML structure

### Deployment

The site automatically deploys to Vercel on push to main branch. The `vercel.json` configuration handles:
- Clean URLs (removing .html extensions)
- Security headers (X-Frame-Options, CSP, etc.)
- PHP serverless function routing

### Important Notes

- No build process or package manager needed
- All assets are served directly
- Google Search Console verified via meta tag
- Contact form currently non-functional (placeholder PHP)