# Hudson Valley Solar Facts

Pro-solar advocacy website countering misinformation about solar energy in Hudson Valley, NY.

**Live site:** https://hvsolarfacts.org
**Repo:** github.com/jefdiesel/solar

---

## Quick Start - Resume Adding Pages

```bash
# 1. Copy an existing FAQ page as template
cp solar-fire-risk.html solar-NEW-TOPIC.html

# 2. Edit the new file:
#    - Update <title>, meta description, og tags
#    - Update canonical URL
#    - Update JSON-LD schema
#    - Update header image and content
#    - Add related links

# 3. Add to sitemap.xml

# 4. Link from faq.html and relevant pages

# 5. Push
git add -A && git commit -m "Add NEW-TOPIC page" && git push
```

Cloudflare auto-deploys on push to main.

---

## Tech Stack

| Component | Details |
|-----------|---------|
| Hosting | Cloudflare Pages |
| Domain | hvsolarfacts.org |
| Styles | Static CSS (`styles.css`) |
| Analytics | Google Analytics `G-W5H9W9SPQX` |
| Forms | Formspree (contact: `mnjnwpvl`) |
| E-commerce | Snipcart (configured, merch not active) |

---

## Current Pages (30 total)

### Main Navigation
| Page | Purpose |
|------|---------|
| `index.html` | Homepage |
| `fire-myth.html` | Castleton fire debunked |
| `farmland.html` | Solar is 0.5% of farmland loss |
| `watershed.html` | Solar protects water quality |
| `energy.html` | Local energy benefits |
| `who-are-they.html` | SSRNY opposition exposed |
| `support.html` | Donations, merch, contact |

### Secondary Pages
| Page | Purpose |
|------|---------|
| `claims-exposed.html` | Line-by-line fact checks |
| `about.html` | Who we are (FAQ format) |
| `sources.html` | All citations |

### Project/Process Pages
| Page | Purpose |
|------|---------|
| `copake-solar.html` | Shepherd's Run project details (42MW) |
| `columbia-county-energy.html` | County's ~36MW existing solar |
| `community-solar.html` | How to subscribe and save 10% |
| `ores-permitting.html` | NY solar permitting explained |

### FAQ Hub + Individual FAQs
| Page | Question Answered |
|------|-------------------|
| `faq.html` | **Hub linking all FAQs** |
| `solar-fire-risk.html` | Do solar farms cause fires? |
| `solar-property-values.html` | Do they lower property values? |
| `solar-panel-recycling.html` | Can panels be recycled? |
| `solar-panels-toxic.html` | Are panels toxic? |
| `solar-farm-noise.html` | Are solar farms noisy? |
| `solar-glare.html` | Do they cause glare? |
| `solar-panels-winter.html` | Do they work in winter? |
| `solar-emf-radiation.html` | Do they emit radiation/EMF? |
| `solar-wildlife.html` | Do they harm wildlife? |
| `agrivoltaics.html` | Can you farm under panels? |

### Economic Pages
| Page | Purpose |
|------|---------|
| `solar-jobs.html` | Employment opportunities |
| `pilot-taxes.html` | How PILOT tax payments work |

### Town Pages (3 built, ~15 pending)
| Page | Status |
|------|--------|
| `solar-hudson-ny.html` | Done - imports 100% electricity |
| `solar-claverack-ny.html` | Done - has 7.5MW ELP solar |
| `solar-kinderhook-ny.html` | Done - has 7.5MW since 2020 |

---

## Images Available

| File | Best Use |
|------|----------|
| `drone_solar.jpeg` | Aerial/overview pages |
| `solar_farm.jpg` | Solar project pages |
| `solar_install.jpeg` | Jobs/workers/economic pages |
| `columbia_farm.jpeg` | Farmland/agriculture pages |
| `hudson.webp` | Hudson city pages |
| `hudon_river.jpg` | Watershed pages |
| `poughkeepsie.webp` | Dutchess County pages |
| `albany.jpg` | State/policy pages |

---

## Page Template Structure

Every page includes:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="icon" type="image/svg+xml" href="/favicon.svg">

  <!-- Google Analytics -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-W5H9W9SPQX"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-W5H9W9SPQX');
  </script>

  <title>PAGE TITLE | Hudson Valley Solar Facts</title>
  <meta name="description" content="150-160 char description">

  <!-- Open Graph -->
  <meta property="og:title" content="PAGE TITLE | Hudson Valley Solar Facts">
  <meta property="og:description" content="Short description">
  <meta property="og:type" content="article">
  <meta property="og:image" content="https://hvsolarfacts.org/IMAGE.jpg">
  <meta property="og:site_name" content="Hudson Valley Solar Facts">
  <meta name="twitter:card" content="summary_large_image">

  <!-- Canonical -->
  <link rel="canonical" href="https://hvsolarfacts.org/PAGE.html">

  <!-- JSON-LD Schema (use FAQPage for question pages) -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [{
      "@type": "Question",
      "name": "The question?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "The answer..."
      }
    }]
  }
  </script>

  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <nav class="nav"><!-- Standard nav --></nav>

  <header class="page-header" style="background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('IMAGE.jpg') center/cover no-repeat; min-height: 55vh; display: flex; align-items: center;">
    <div style="margin-left: 10%;">
      <span class="tag tag-success">Tag</span>
      <h1 class="mt-4" style="color: white; max-width: 900px;">Page Title</h1>
      <p class="lead" style="color: rgba(255,255,255,0.9); max-width: 900px;">Subtitle</p>
    </div>
  </header>

  <article class="article">
    <div class="container">
      <div class="article-content">
        <!-- Content here -->
      </div>
    </div>
  </article>

  <footer class="footer"><!-- Standard footer with FAQ link --></footer>

  <script>
    document.getElementById('nav-toggle').addEventListener('click', function() {
      document.getElementById('nav-links').classList.toggle('active');
    });
  </script>
</body>
</html>
```

---

## Adding a New Page - Full Checklist

### 1. Create HTML file
- Copy similar existing page as template
- Update all meta tags (title, description, og, canonical)
- Update JSON-LD schema
- Update header image and text
- Write content
- Add "Related Facts" section linking to other pages

### 2. Update sitemap.xml
```xml
<url>
  <loc>https://hvsolarfacts.org/new-page.html</loc>
  <lastmod>2025-01-05</lastmod>
  <changefreq>monthly</changefreq>
  <priority>0.7</priority>
</url>
```

### 3. Add links from other pages
- **FAQ pages:** Add to `faq.html` hub
- **Town pages:** Add to `columbia-county-energy.html`
- **Topic pages:** Add to "Related Facts" on relevant pages

### 4. Deploy
```bash
git add -A
git commit -m "Add PAGE-NAME - brief description"
git push
```

---

## Pending Work

### Town Pages to Build (~15)

| Town | Solar Status | Priority |
|------|--------------|----------|
| Greenport | 7MW ELP project | High |
| Ghent | 4.3MW ELP project | High |
| Livingston | 6.3MW ELP project | High |
| Clermont | 3.9MW Roe Jan | High |
| Copake | Shepherd's Run proposed | High |
| Chatham | No major project | Medium |
| Hillsdale | No major project | Medium |
| Ancram | No major project | Medium |
| Taghkanic | No major project | Medium |
| Germantown | No major project | Low |
| Stockport | No major project | Low |
| Stuyvesant | No major project | Low |
| New Lebanon | No major project | Low |
| Canaan | No major project | Low |
| Austerlitz | No major project | Low |

### More FAQ Topics to Consider

| Topic | Target Keyword |
|-------|----------------|
| `solar-decommissioning.html` | What happens at end of life |
| `solar-vs-wind.html` | Solar vs wind comparison |
| `rooftop-vs-utility.html` | Why we need both |
| `solar-batteries.html` | Storage questions |
| `solar-grid-reliability.html` | Intermittency |
| `how-solar-works.html` | Educational basic |
| `ny-climate-law.html` | CLCPA explained |
| `solar-flooding.html` | Stormwater concerns |
| `solar-heat-island.html` | Temperature effects |

---

## Key Facts Reference

### Columbia County Solar (~36MW existing)
| Project | Capacity | Location |
|---------|----------|----------|
| ELP Greenport | 7 MW | Greenport |
| ELP Kinderhook | 7.5 MW | Kinderhook (since 2020) |
| ELP Claverack | 7.5 MW | Claverack |
| ELP Ghent | 4.3 MW | Ghent |
| ELP Livingston | 6.3 MW | Livingston |
| ELP Roe Jan | 3.9 MW | Clermont |

### Shepherd's Run (Proposed)
- **Capacity:** 42 MW
- **Location:** Copake
- **Homes powered:** ~9,500
- **Status:** Under ORES review (Case 21-02553)

### NY Grid Mix (2024)
- Natural gas: 48.7%
- Nuclear: 24.5%
- Hydro: 18.2%
- Wind: 4.8%
- Solar: 2.1%
- Other: 1.7%

### Key Stats
- Solar = 0.5% of NY farmland loss (State Comptroller, Nov 2024)
- NY lost 14% of farms 2012-2022
- Hudson city imports 100% of electricity
- CLCPA targets: 70% renewable by 2030, 100% zero-emission by 2040

---

## Forms Configuration

| Form | Formspree ID | Page |
|------|--------------|------|
| Contact | `mnjnwpvl` | support.html |

Newsletter form removed per user request.

---

## Deployment

- **Host:** Cloudflare Pages
- **Auto-deploy:** Push to `main` triggers deployment
- **Domain:** Configured in Workers & Pages > Custom domains

### Local Development
```bash
# Simple local server
python -m http.server 8000
# Then open http://localhost:8000
```

---

## Original Project Goals

**Position:** Pro-solar expansion. Not pro-Hecate, not anti-regulation. Solar is good for the county. Misinformation is bad.

**Target audience:** Newer Columbia County residents (weekenders, remote workers, young families) who care about climate but have been confused by SSRNY's fake environmental framing.

**Opposition:** Sensible Solar for Rural NY (sensiblesolarny.org) - small group using "environment" as cover for general opposition to change.

**Core rebuttals:**
1. Fire risk is a lie (Castleton was a brush fire, zero panel damage)
2. Solar is 0.5% of farmland loss (economics is killing farms, not solar)
3. Solar is GOOD for watersheds (no septic, no fertilizer, no impervious surface)
4. Columbia County deserves local clean energy (currently imports 100%)

---

## Resources

### Primary Sources
- [NY State Comptroller Agriculture Report](https://www.osc.ny.gov/files/reports/pdf/profile-of-agriculture-in-nys.pdf)
- [ORES Permit Applications](https://ores.ny.gov/permit-applications)
- [NYISO Power Trends](https://www.nyiso.com/power-trends)
- [NYSERDA Community Solar](https://www.nyserda.ny.gov/All-Programs/NY-Sun/Solar-for-Your-Home/Community-Solar)

### Allies
- [Friends of Columbia Solar](https://www.friendsofcolumbiasolar.org)
- [NY Renews](https://nyrenews.org)
