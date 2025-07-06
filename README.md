<a name="readme-top"></a>

# Full-stack Realtime Google Docs Clone using Next.js 15 and Convex

![Full-stack Realtime Google Docs Clone using Next.js 15 and Convex](/.github/images/img_main.png 'Full-stack Realtime Google Docs Clone using Next.js 15 and Convex')


<!-- Table of Contents -->
<details>

<summary>

# :notebook_with_decorative_cover: Table of Contents

</summary>

- [Folder Structure](#bangbang-folder-structure)
- [Getting Started](#toolbox-getting-started)
- [Screenshots](#camera-screenshots)
- [Tech Stack](#gear-tech-stack)
- [Stats](#wrench-stats)
- [Contribute](#raised_hands-contribute)
- [Acknowledgements](#gem-acknowledgements)
- [Buy Me a Coffee](#coffee-buy-me-a-coffee)
- [Follow Me](#rocket-follow-me)
- [Learn More](#books-learn-more)
- [Deploy on Vercel](#page_with_curl-deploy-on-vercel)
- [Give A Star](#star-give-a-star)
- [Star History](#star2-star-history)
- [Give A Star](#star-give-a-star)

</details>

## :bangbang: Folder Structure

Here is the folder structure of this app.

```bash
google-docs-clone/
  |- convex/
    |-- _generated/
    |-- .env.example
    |-- .env.local
    |-- auth.config.ts
    |-- documents.ts
    |-- environment.d.ts
    |-- schema.ts
  |- public/
    |-- blank-document.svg
    |-- business-letter.svg
    |-- cover-letter.svg
    |-- letter.svg
    |-- logo.svg
    |-- project-proposal.svg
    |-- resume.svg
    |-- software-proposal.svg
  |- src/
    |-- app/
        |--- (home)/
        |--- api/
        |--- documents/
        |--- apple-icon.png
        |--- error.tsx
        |--- favicon.ico
        |--- globals.css
        |--- icon1.png
        |--- icon2.png
        |--- layout.tsx
        |--- not-found.tsx
    |-- components/
        |--- ui/
        |--- convex-client-provider.tsx
        |--- fullscreen-loader.tsx
        |--- remove-dialog.tsx
        |--- rename-dialog.tsx
    |-- config/
        |--- editor.ts
        |--- index.ts
    |-- constants/
        |--- index.ts
    |-- extensions/
        |--- font-size.ts
        |--- line-height.ts
    |-- hooks/
        |--- use-debounce.ts
        |--- use-search-param.tsx
    |-- lib/
        |--- utils.ts
    |-- store
        |--- use-editor-store.ts
    |-- middleware.ts
  |- .env.example
  |- .env.local
  |- .eslintrc.json
  |- .gitignore
  |- .prettierrc.json
  |- .prettierrc.mjs
  |- bun.lockb
  |- components.json
  |- environment.d.ts
  |- liveblocks.config.ts
  |- next.config.ts
  |- package.json
  |- postcss.config.mjs
  |- README.md
  |- tailwind.config.ts
  |- tsconfig.json
```

<br />

## :toolbox: Getting Started

1. Make sure **Git** and **NodeJS** is installed.
2. Clone this repository to your local computer.
3. Create `.env.local` file in **root** and **convex** directory.
4. Contents of `.env.local`:

```env
# disabled clerk and next.js telemetry
NEXT_TELEMETRY_DISABLED=1
CLERK_TELEMETRY_DISABLED=1

# app base url
NEXT_PUBLIC_APP_BASE_URL="http://localhost:3000"

# convex deployment & url
CONVEX_DEPLOYMENT="dev:<deployment-id>" # team: <team-id>, project: <project-id>
NEXT_PUBLIC_CONVEX_URL="https://<deployment-id>.convex.cloud"

# clerk auth keys
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="pk_test_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
CLERK_SECRET_KEY="sk_test_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

# liveblocks keys
NEXT_PUBLIC_LIVEBLOCKS_API_KEY="pk_dev_-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
LIVEBLOCKS_SECRET_KEY="sk_dev_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

```

5. Contents of `convex/.env.local`:

```env
# clerk issuer url (go to your clerk dashboard > JWT Templates > New template > Convex > Save and copy your Issuer URL)
CLERK_ISSUER_URL=https://example-id.clerk.accounts.dev

```

### 6. App Base URL

Set the `NEXT_PUBLIC_APP_BASE_URL` to `http://localhost:3000` where your app will be running locally or in production.

### 7. Convex Deployment

- Visit the Convex website: [https://convex.dev](https://convex.dev)
- Log in to your Convex account or sign up if you don't have one.
- Once logged in, navigate to the "Deployments" section.
- Create a new deployment or select an existing one.
- Replace `<deployment-name>`, `<team-name>`, and `<project-name>` in the `.env.local` file with your Convex deployment details.
- In the Convex dashboard, find the public URL associated with your deployment.
- Replace `<your-convex-url>` in the `.env.local` file with your Convex public URL.

### 8. Clerk Authentication Keys

- Visit the Clerk dashboard: [https://clerk.dev](https://clerk.dev)
- Log in to your Clerk account or sign up if you don't have one.
- Go to the "Projects" section and select your project.
- Navigate to the "API Keys" tab.
- Copy the "Publishable Key" and replace `<your-clerk-publishable-key>` in the `.env.local` file with the copied key.
- Copy the "Secret Key" and replace `<your-clerk-secret-key>` in the `.env.local` file with the copied key.
- Go to your Clerk dashboard > JWT Templates > New template > Convex.
- In the **Claims section** add `"organization_id": "{{org.id}}"` along with the existing json values.
- Click on save and copy the **Issuer url**.
- Replace `<your-clerk-issuer-url>` with the url that you copied.
- Also, go to Convex dashboard > Settings > Environment Variables > Add `CLERK_ISSUER_URL` variable with value that you copied.

### 9. Liveblocks API Keys

- Visit the Liveblocks website > dashboard.
- Navigate to API settings or keys section.
- Generate or locate your API key and secret.
- Set `NEXT_PUBLIC_LIVEBLOCKS_API_KEY` and `LIVEBLOCKS_SECRET_KEY` in the `.env` file according to the obtained information.

10. Install Project Dependencies using `npm install --legacy-peer-deps` or `yarn install --legacy-peer-deps` or `bun install --legacy-peer-deps`.

11. Now app is fully configured 👍 and you can start using this app using either one of `npm run dev` or `yarn dev` or `bun dev`.

**NOTE:** Please make sure to keep your API keys and configuration values secure and do not expose them publicly.

## :camera: Screenshots

![Modern UI/UX](/.github/images/img1.png 'Modern UI/UX')

![Realtime Tiptap Editor](/.github/images/img2.png 'TiptapRealtime Tiptap Editor')

![Mentions, Replies and Reactions](/.github/images/img3.png 'Mentions, Replies and Reactions')

## :gear: Tech Stack

[![React JS](https://skillicons.dev/icons?i=react 'React JS')](https://react.dev/ 'React JS') [![Next JS](https://skillicons.dev/icons?i=next 'Next JS')](https://nextjs.org/ 'Next JS') [![Typescript](https://skillicons.dev/icons?i=ts 'Typescript')](https://www.typescriptlang.org/ 'Typescript') [![Tailwind CSS](https://skillicons.dev/icons?i=tailwind 'Tailwind CSS')](https://tailwindcss.com/ 'Tailwind CSS') [![Vercel](https://skillicons.dev/icons?i=vercel 'Vercel')](https://vercel.app/ 'Vercel')



<br />
<p align="right">(<a href="#readme-top">back to top</a>)</p>
