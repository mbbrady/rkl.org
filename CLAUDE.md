# CLAUDE.md - Resonant Knowledge Lab Website (Public Repo)

**Project**: Resonant Knowledge Lab - Public Website
**Repository**: Public website repo
**Type**: Hugo static site
**URL**: https://resonantknowledgelab.org

---

## Project Overview

This is the **public website repository** for Resonant Knowledge Lab (RKL), a Virginia-based 501(c)(3) nonprofit dedicated to advancing ethical, community-governed artificial intelligence.

**Mission**: To make human knowledge — in all its cultural, institutional, and environmental forms — discoverable, accessible, and securely interoperable with AI.

**Tagline**: Ethical AI for Living Knowledge

---

## Technology Stack

- **Static Site Generator**: Hugo
- **Theme**: Clarity (light variant)
- **Language**: English (en-us)
- **Accent Color**: #0F4C81 (blue)
- **Deployment**: GitHub Pages / Netlify / Vercel (TBD)

---

## Repository Structure

```
rkl.org/
├── archetypes/          # Hugo content templates
├── content/             # Website content (Markdown)
│   ├── _index.md           # Home page
│   ├── about.md            # Mission, vision, principles
│   ├── programs.md         # Core program areas
│   ├── data-ethics.md      # Data ethics page
│   └── projects/           # Future project pages
│
├── static/              # Static assets (images, files)
├── themes/clarity/      # Hugo Clarity theme
├── public/              # Built site (DO NOT commit - gitignored)
├── config.toml          # Site configuration
└── .gitignore           # Excludes build artifacts
```

---

## Key Content Pages

### Home Page (`content/_index.md`)
- Tagline: "Ethical AI for Living Knowledge"
- Mission statement (one-sentence version)
- Welcome text

### About Page (`content/about.md`)
- Full mission and vision
- Guiding principles (5 core principles)
- About RKL section

### Programs Page (`content/programs.md`)
- Five core program areas
- 2025-2027 goals
- Current projects (Closed RAG Initiative, Arctic AI)
- Call to action for collaboration

### Data Ethics Page (`content/data-ethics.md`)
- (Existing content - may need updating)

---

## Mission Statement (Website Version)

### Single Sentence (Most Used)
> Our mission is to make human knowledge — in all its cultural, institutional, and environmental forms — discoverable, accessible, and securely interoperable with AI.

### Tagline (Shortest)
> Ethical AI for Living Knowledge

### Two Paragraphs (For About Page)
> Resonant Knowledge Lab (RKL) is a nonprofit research and development organization dedicated to advancing ethical, community-governed artificial intelligence.
>
> We explore how local, indigenous, and organizational knowledge can be securely integrated into AI through transparent, auditable architectures that protect privacy, context, and data sovereignty.

---

## Core Programs (Brief)

1. **Ethical AI & Knowledge Stewardship**
2. **Local & Indigenous Knowledge Systems**
3. **Organizational Knowledge Resilience**
4. **Open Infrastructure & Secure Contexts**
5. **Public Education & Collaboration**

See `/content/programs.md` for full details.

---

## Development Workflow

### Local Development
```bash
cd /home/mike/project/rkl/rkl.org

# Preview with drafts
hugo server -D

# Preview without drafts (production mode)
hugo server

# View at: http://localhost:1313
```

### Building for Production
```bash
hugo

# Output goes to /public/ directory
# Deploy contents of /public/ to hosting provider
```

### Git Workflow
```bash
# After making content changes
git status
git add content/
git commit -m "Update about page with new mission statement"
git push origin main
```

---

## Configuration (`config.toml`)

Key settings:
- **baseURL**: `https://resonantknowledgelab.org/`
- **title**: Resonant Knowledge Lab
- **theme**: clarity
- **description**: Full mission statement for SEO
- **tagline**: "Ethical AI for Living Knowledge"

Navigation menu order:
1. About
2. Programs
3. Data Ethics
4. Contact

---

## Related Repositories

### Private Organizational Repo
- **Location**: `/home/mike/project/rkl/rkl-program/`
- **GitHub**: `github.com/mbbrady/rkl` (private)
- **Purpose**: Full nonprofit organizational structure
- **Contains**: Board documents, compliance filings, detailed mission docs

**Content relationship**:
- This website uses *public versions* of mission content
- Full mission documents live in private repo
- When mission changes, update both repos

---

## Content Guidelines

### This is a PUBLIC repository

Everything here is visible to the world. Guidelines:

✅ **DO include**:
- Mission, vision, and values
- Program descriptions
- Blog posts and updates
- Public research findings
- Contact information
- Educational content

❌ **DO NOT include**:
- Board member personal details
- Financial information
- Donor lists
- Internal strategy documents
- Anything not intended for public view

### Writing Style

- Clear and accessible language
- Focus on impact and values
- Avoid jargon where possible
- When using technical terms, explain them
- Emphasize ethics, community, and transparency
- Use active voice

### Tone

- Professional but approachable
- Passionate about ethical AI
- Respectful of diverse knowledge systems
- Transparent about methods and principles
- Invitation to collaborate

---

## Hugo Tips

### Creating New Pages
```bash
hugo new content/contact.md
hugo new content/blog/first-post.md
```

### Working with Drafts
```markdown
---
title: "New Page"
draft: true
---
```
Drafts only show with `hugo server -D`

### Front Matter
Each content file starts with YAML front matter:
```yaml
---
title: "Page Title"
description: "SEO description"
date: 2025-10-14
---
```

### Markdown Formatting
- Headers: `## Header`, `### Subheader`
- Bold: `**text**`
- Links: `[text](url)`
- Lists: `- item` or `1. item`

---

## Deployment Options

### GitHub Pages (Free)
```bash
# In repository settings on GitHub:
# Settings → Pages → Source: gh-pages branch
```

### Netlify (Recommended for Hugo)
- Connect GitHub repo
- Build command: `hugo`
- Publish directory: `public`
- Auto-deploy on push

### Vercel
- Import GitHub repo
- Framework preset: Hugo
- Auto-deploy on push

---

## SEO & Analytics

### Current SEO Setup
- Site description in `config.toml`
- Page descriptions in front matter
- `robots.txt` enabled
- Sitemap auto-generated

### Future Enhancements
- Add Google Analytics (pending board approval)
- Set up Google Search Console
- Add social media meta tags
- Create Open Graph images

---

## Maintenance Tasks

### Regular Updates
- Update mission content when changed in private repo
- Add new blog posts about projects and research
- Update program descriptions as initiatives launch
- Add case studies and impact stories

### Before Publishing
- Run `hugo` to check for build errors
- Preview locally with `hugo server`
- Check all links work
- Review for typos
- Ensure content aligns with nonprofit mission

---

## Current Status

- ✅ Hugo site configured
- ✅ Clarity theme installed
- ✅ Mission and vision updated
- ✅ Core pages created (Home, About, Programs)
- ⏳ Contact page (needs creation)
- ⏳ Blog setup (future)
- ⏳ Domain DNS configuration (pending)
- ⏳ Hosting/deployment (TBD: GitHub Pages, Netlify, or Vercel)

---

## Helpful Commands

### Preview the site
```bash
cd /home/mike/project/rkl/rkl.org && hugo server -D
```

### Build for production
```bash
cd /home/mike/project/rkl/rkl.org && hugo
```

### Check for broken links
```bash
hugo server &
wget --spider -r -nd -nv -l 3 http://localhost:1313/ 2>&1 | grep -B1 'broken link'
```

### Search content
```bash
grep -r "keyword" content/
```

---

## Key Principles for AI Assistants

When working with this website:

1. **Public Content Only**: Everything here is visible to the world
2. **Mission Alignment**: All content should reflect RKL's ethical AI mission
3. **Accessibility**: Write clearly for diverse audiences
4. **Consistency**: Match tone and style of existing content
5. **SEO-Friendly**: Use descriptive titles and meta descriptions
6. **Build Before Deploy**: Always test with `hugo` before pushing

---

## Questions & Support

- **Hugo Documentation**: https://gohugo.io/documentation/
- **Clarity Theme**: https://github.com/chipzoller/hugo-clarity
- **Mission Content**: See private repo `rkl-program/` for full versions
- **Organizational Context**: See `../rkl-program/CLAUDE.md`

---

**Last updated**: 2025-10-14
**Status**: Active development
**Next milestone**: Set up hosting and deploy live site
