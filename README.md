# Portfolio Website

A modern, responsive personal portfolio website for **Suchit Mangave**, Software Engineer. It's a static site (no backend, no build step) built with HTML, CSS, and **jQuery**, featuring a glassmorphism UI, animated hero section with a typing effect, 3D tilt micro-animations, scroll-reveal animations, a filterable project showcase, and a working contact form via EmailJS.

🔗 **Live site:** add your deployed URL here (e.g. GitHub Pages / Netlify link)

## Features

- **Hero section** with a Particles.js animated background and a Typed.js typing effect
- **About** section with profile summary and contact details
- **Skills** section driven by `skills.json`, grouped by category (Backend, Frontend, Tools) with proficiency levels and percentages
- **Education** timeline
- **Work / Projects** showcase driven by `projects/projects.json`, filterable by category (Basic Web, MERN, Android, LAMP) using Isotope.js
- **Experience** page with its own layout, scroll-reveal timeline animation, and Tawk.to live chat widget
- **Contact form** that sends messages via EmailJS (`emailjs.sendForm`) — no server required
- **Contact** section with social links (LinkedIn, GitHub, Twitter, Telegram, Instagram, Dev.to)
- Scroll-spy navigation (active nav link updates as you scroll) and smooth-scroll anchor links
- 3D tilt hover effect on images (Vanilla-Tilt.js) and scroll-reveal animations (ScrollReveal.js)
- Custom **404** error page
- Basic anti-inspection measures: right-click disabled (`oncontextmenu="return false"`) and DevTools shortcuts (F12, Ctrl+Shift+I/C/J, Ctrl+U) blocked via JS
- Fully responsive layout

## Tech Stack

This is a static, no-build site — **jQuery-based**, not a JS framework and not fully dependency-free vanilla JS.

| Library | Purpose |
|---|---|
| HTML5 / CSS3 | Page structure and styling |
| [jQuery 3.6.0](https://jquery.com/) | DOM manipulation, event handling, scroll-spy, smooth scroll, form submission (used across `script.js`, `projects/script.js`, `experience/script.js`, `404.js`) |
| [Particles.js](https://vincentgarreau.com/particles.js/) | Animated hero background (`assets/js/particles.min.js` + config in `assets/js/app.js`) |
| [Typed.js](https://github.com/mattboldt/typed.js/) | Typing/erasing text animation in the hero section |
| [Vanilla-Tilt.js](https://micku7zu.github.io/vanilla-tilt.js/) | 3D tilt effect on images |
| [ScrollReveal.js](https://scrollrevealjs.org/) | Scroll-triggered reveal animations |
| [Isotope.js](https://isotope.metafizzy.co/) | Filterable/sortable masonry grid for the Projects page |
| [EmailJS](https://www.emailjs.com/) | Sends the contact form directly from the client, no backend |
| [Tawk.to](https://www.tawk.to/) | Embedded live chat widget (on the Experience page) |
| [Font Awesome](https://fontawesome.com/) | General UI icons |
| [Devicon](https://devicon.dev/) | Technology/skill icons |

All third-party libraries are pulled from CDNs (jsDelivr, cdnjs, unpkg) except Particles.js, which is vendored locally in `assets/js/particles.min.js`. No package manager, bundler, or `node_modules` is involved.

## Project Structure

```
Protfolio-website/
├── index.html              # Main landing page (Home, About, Skills, Education, Work, Contact)
├── 404.html                 # Custom 404 error page
├── skills.json               # Skills data (name, icon, category, level, percentage)
├── assets/
│   ├── css/
│   │   ├── style.css         # Main site styles
│   │   └── 404.css           # 404 page styles
│   ├── js/
│   │   ├── app.js            # Particles.js config (plain JS)
│   │   ├── script.js         # Navbar, scroll-spy, smooth scroll, contact form (jQuery)
│   │   ├── particles.min.js  # Particles.js library (vendored)
│   │   └── 404.js            # 404 page nav toggle + devtools blocking (jQuery)
│   └── images/                # Site images and project screenshots
├── experience/
│   ├── index.html             # Experience page
│   ├── script.js
│   └── style.css
└── projects/
    ├── index.html              # Projects showcase page
    ├── projects.json            # Project data (name, description, image, category, links)
    ├── script.js
    └── style.css
```

## Getting Started

This is a static website with no build step required.

1. **Clone the repository**
   ```bash
   git clone https://github.com/SuchitMangave/Protfolio-website.git
   cd Protfolio-website
   ```

2. **Open it locally**

   Simply open `index.html` in your browser, or serve it with a local server (recommended, since the Projects page fetches `projects.json` via `fetch()`, which most browsers block under the `file://` protocol):

   ```bash
   # Using Python
   python3 -m http.server 8000

   # Using Node (http-server)
   npx http-server .
   ```

   Then visit `http://localhost:8000` in your browser. An internet connection is needed for the CDN-hosted libraries (jQuery, Particles.js config assets, Typed.js, ScrollReveal, Isotope, EmailJS, Tawk.to, Font Awesome, Devicon) to load.

   > **Note:** the contact form uses an EmailJS public key and service/template IDs hardcoded in `assets/js/script.js` (`emailjs.init(...)`, `emailjs.sendForm(...)`). If you fork this project, replace them with your own EmailJS credentials, or the form will submit to the original owner's account.

## Customization

- **Skills:** edit `skills.json` to add/remove/update technologies, categories, and proficiency levels.
- **Projects:** edit `projects/projects.json` to add/remove projects — each entry supports a name, description, image, category, and view/code links.
- **Personal info & socials:** update the relevant sections directly in `index.html` (About, Contact, social links in the header).
- **Styling:** update `assets/css/style.css` for global styles, or the page-specific stylesheets in `experience/` and `projects/`.

## Contact

- **Email:** suchitmangave@gmail.com
- **LinkedIn:** [suchit-mangave](https://www.linkedin.com/in/suchit-mangave)
- **GitHub:** [@SuchitMangave](https://github.com/SuchitMangave)
- **Twitter:** [@suchit_mangave](https://twitter.com/suchit_mangave)

## License

No license file is currently included in this repository. Consider adding one (e.g. MIT) if you'd like others to reuse this code.
