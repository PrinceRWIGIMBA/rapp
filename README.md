# RAPP Blog – CMS Edition

This project uses **Netlify CMS** (now Decap CMS) to let you manage all content through a visual admin interface at `/admin`.

## Project Structure

```
rapp/
├── public/
│   ├── admin/
│   │   ├── config.yml     ← CMS configuration (all fields defined here)
│   │   └── index.html     ← CMS admin app
│   └── images/            ← Uploaded media goes here
├── src/
│   ├── data/
│   │   ├── site.json      ← Site name, contact info, social links
│   │   ├── home.json      ← Home page (hero, stats, features, news)
│   │   ├── about.json     ← About page (team, values, milestones)
│   │   ├── contact.json   ← Contact page (offices, form topics)
│   │   ├── partners.json  ← Partners page (tiers, partner cards)
│   │   ├── donate.json    ← Donate page (amounts, impact messages)
│   │   ├── posts.json     ← All blog posts
│   │   └── projects.json  ← All projects
│   ├── pages/             ← Astro pages (read from data/*.json)
│   ├── components/        ← Nav, Footer, etc.
│   └── layouts/           ← Base HTML layout
└── netlify.toml           ← Netlify deployment config
```

## Running Locally

```bash
npm install
npm run dev
```

Open http://localhost:4321

## Deploying to Netlify

1. Push this project to a GitHub repository.
2. Connect the repo to [Netlify](https://netlify.com).
3. Netlify auto-detects the `netlify.toml` config and runs `npm run build`.
4. In Netlify dashboard → **Identity** → Enable Identity.
5. In Identity → **Services** → Enable **Git Gateway**.
6. Invite yourself as a user under **Identity → Invite users**.

## Accessing the CMS

Once deployed, go to: `https://your-site.netlify.app/admin`

Log in with your Netlify Identity credentials and you can:

- ✏️ Edit site settings (name, email, phone, socials)
- 🏠 Edit every section of the Home page
- ℹ️ Manage About page (team members, values, milestones, story)
- 📞 Update Contact offices and form topics
- 🤝 Manage partner tiers and cards
- 💛 Update donate page amounts and impact messages
- 📝 Create, edit, delete blog posts (with rich text editor)
- 🗂️ Create, edit, delete projects (with stats, gallery, full body)

All changes are committed directly to your Git repository, which triggers a new Netlify deploy automatically.

## Local CMS Testing (without Netlify)

You can test the CMS locally using Netlify's local proxy:

```bash
npx netlify-cms-proxy-server
# In another terminal:
npm run dev
```

Then go to http://localhost:4321/admin
