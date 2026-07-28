# ToolSphere.online

25 free, fully client-side tools (YouTube SEO, Instagram, Finance, Utility, Design/Developer, Learning) built with
plain HTML, CSS and JavaScript — no framework, no build step. Ready to push to GitHub and deploy on Vercel.

## Folder structure

```
toolsphere/
  index.html            → Homepage
  tools.html            → All-tools directory (filterable)
  faq.html, about.html, contact.html, blog.html
  blog/                 → 2 blog posts
  legal/                → privacy, terms, disclaimer, cookies, refund
  tools/                → 25 individual tool pages
  assets/css/style.css  → All styling
  assets/js/common.js   → Shared JS (nav, copy buttons)
  assets/js/safe-prompt.js → Content safety filter for the image generator
  robots.txt, sitemap.xml, 404.html, vercel.json
```

## GitHub par upload (step-by-step)

1. https://github.com par jaake naya repository banao (e.g. `toolsphere`), **public**, README add mat karo (yeh
   zip already README ke saath hai).
2. Apne computer par is folder ko unzip karo.
3. Terminal / Git Bash kholo, unzip ki hui folder ke andar jaao:
   ```
   cd toolsphere
   git init
   git add .
   git commit -m "Initial commit - ToolSphere website"
   git branch -M main
   git remote add origin https://github.com/<your-username>/toolsphere.git
   git push -u origin main
   ```
   (`<your-username>` apna GitHub username daalo)

## Vercel se deploy (step-by-step)

1. https://vercel.com par jaake GitHub account se sign in karo.
2. Dashboard me **"Add New" → "Project"** click karo.
3. Apni GitHub repo (`toolsphere`) select karo → **Import**.
4. Framework Preset: **"Other"** select karo (ya "Static") — koi build command nahi chahiye, kyunki yeh plain
   HTML site hai. Root directory default rakho.
5. **Deploy** click karo. 30-60 second me live ho jayega, e.g. `toolsphere.vercel.app`.

## Apna domain (toolsphere.online) connect karna

1. Vercel project ke andar **Settings → Domains** me jaao.
2. `toolsphere.online` add karo.
3. Vercel jo Nameservers ya A/CNAME record dikhaye, wahi apne domain registrar (jahan se domain kharida hai) ke
   DNS settings me daal do.
4. 10 minute se 24 hours ke andar domain live ho jayega (DNS propagation time lagta hai).

## Monetization (AdSense waghera) ke liye

- Sabhi ad slots `<div class="ad-slot">` already har page par lagi hui hain — bas apna AdSense (ya kisi bhi
  network ka) `<script>` tag `assets/js/common.js` se pehle `<head>` ya ad-slot div ke andar daal dena.
- Legal pages (Privacy, Terms, Disclaimer, Cookies, Refund) already ready hain — AdSense approval ke liye zaroori
  hain.
- Contact email: `toolsphereweb@gmail.com` sabhi pages par already set hai.

## Image Generator ke baare me — zaroori jaankari

Image Generator tool ek **free, no-key, public endpoint** (Pollinations.ai) use karta hai — isiliye "unlimited"
free image generation kaam karta hai bina kisi API key ke. Agar aap chaho to apna khud ka paid API (OpenAI,
Stability AI, Replicate) use karna chaho better quality/reliability ke liye, to `assets/js` me ek naya script
bana ke `tools/image-generator.html` ka fetch call update karna hoga — us case me API key backend (serverless
function) me rakhni hogi, kabhi bhi frontend JS me directly nahi (warna key public ho jayegi).

Content safety filter `assets/js/safe-prompt.js` me hai — explicit/NSFW/violent keywords block karta hai aur har
prompt me "modest, respectful, fully covered" style automatically add karta hai.

## Local testing

Koi build step nahi chahiye. Bas `index.html` ko browser me kholo, ya:
```
cd toolsphere
python3 -m http.server 8000
```
phir `http://localhost:8000` kholo.
