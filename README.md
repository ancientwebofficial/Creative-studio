# Creative Portfolio & Studio CMS

A premium, modern, fully CMS-driven portfolio template for showcasing image-based creative work. It gives studios, agencies, designers, and freelancers a polished public site plus a Payload CMS to manage portfolio items, categories, homepage sections, branding, SEO, testimonials, FAQs, pricing plans, and media without editing source code.    

![Next.js](https://img.shields.io/badge/Next.js-16.2.6-black?logo=next.js)
![React](https://img.shields.io/badge/React-19.2.4-61DAFB?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript)
![Payload CMS](https://img.shields.io/badge/Payload-CMS-3.85.2-ff6b6b)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-336791?logo=postgresql)
![Supabase](https://img.shields.io/badge/Supabase-Auth%20%26%20Storage-3FCF8E?logo=supabase)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC?logo=tailwind-css)
![Vercel](https://img.shields.io/badge/Deploy-Vercel-000000?logo=vercel)
![Open Source](https://img.shields.io/badge/Open-Source-6E40C9)
![GitHub Stars](https://img.shields.io/badge/dynamic/json?label=GitHub%20Stars&query=%24.stargazers_count&url=https%3A%2F%2Fapi.github.com%2Frepos%2Fancientwebofficial%2FCreative-studio)
![GitHub Forks](https://img.shields.io/badge/dynamic/json?label=GitHub%20Forks&query=%24.forks_count&url=https%3A%2F%2Fapi.github.com%2Frepos%2Fancientwebofficial%2FCreative-studio)
![GitHub Issues](https://img.shields.io/badge/dynamic/json?label=GitHub%20Issues&query=%24.open_issues_count&url=https%3A%2F%2Fapi.github.com%2Frepos%2Fancientwebofficial%2FCreative-studio)

## Demo

- Live Demo: Not published yet
- Repository: https://github.com/ancientwebofficial/Creative-studio
- Documentation: This README and the screenshot placeholders in [docs/screenshots](docs/screenshots)

## Quick Start

```bash
git clone https://github.com/ancientwebofficial/Creative-studio.git
cd Creative-studio
npm install
cp .env.example .env.local
npm run payload:generate-types
npm run payload:migrate
npm run dev
```

Open the site at http://localhost:3000 and the CMS at http://localhost:3000/cms.

## Features

- Responsive design
- Premium UI
- Dark theme
- Dynamic branding
- Dynamic homepage
- Dynamic navigation
- Dynamic hero section
- Featured portfolio work
- Portfolio categories
- Portfolio items
- Owner profile
- Testimonials
- FAQs
- Pricing plans
- Contact page
- Footer
- SEO controls
- Theme settings
- Payload CMS
- Media library
- PostgreSQL support
- Supabase integration
- S3-compatible storage support
- Authentication and admin roles
- Server components
- App Router
- Local development and production build workflow

## Tech Stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js, React, TypeScript, Tailwind CSS |
| CMS | Payload CMS |
| Database | PostgreSQL |
| Auth and storage | Supabase |
| Media storage | S3-compatible object storage (optional) |
| Tooling | ESLint, TSX |
| Deployment | Vercel |

## Project Structure

```text
.
├── .env.example
├── LICENSE
├── next.config.ts
├── package.json
├── public/
├── scripts/
├── src/
│   ├── app/
│   │   ├── (frontend)/
│   │   └── (payload)/
│   ├── components/
│   ├── data/
│   ├── lib/
│   ├── migrations/
│   ├── payload/
│   └── payload-types.ts
├── supabase/
│   └── migrations/
└── tsconfig.json
```

## Installation

### Prerequisites

- Node.js
- npm
- A Supabase project
- A PostgreSQL database
- Payload CMS (included as a dependency)

### Clone the repository

```bash
git clone https://github.com/ancientwebofficial/Creative-studio.git
cd Creative-studio
```

### Install dependencies

```bash
npm install
```

### Configure environment variables

Copy the example file and create a local environment file:

```bash
cp .env.example .env.local
```

The project uses the following environment variables from [.env.example](.env.example):

- NEXT_PUBLIC_SITE_URL: The public URL of the site. Use http://localhost:3000 for local development.
- PAYLOAD_SECRET: A long random secret for Payload CMS encryption and session security.
- PAYLOAD_DATABASE_SCHEMA: The PostgreSQL schema used by Payload. Defaults to payload.
- PAYLOAD_DATABASE_URI: The PostgreSQL connection string for Payload. This is the preferred variable for the Payload database adapter.
- DATABASE_URL: An additional PostgreSQL connection string alias used by the app and seed script.
- NEXT_PUBLIC_SUPABASE_URL: Your Supabase project URL.
- NEXT_PUBLIC_SUPABASE_ANON_KEY: Your Supabase anonymous/publishable key.
- SUPABASE_SERVICE_ROLE_KEY: Your Supabase service role key for server-side admin operations.
- NEXT_PUBLIC_SUPABASE_MEDIA_BUCKET: The Supabase storage bucket to use for media.
- PAYLOAD_S3_BUCKET: The S3-compatible bucket name for Payload media storage.
- PAYLOAD_S3_REGION: The S3 region.
- PAYLOAD_S3_ENDPOINT: The S3-compatible endpoint URL.
- PAYLOAD_S3_ACCESS_KEY_ID: The access key ID for S3-compatible storage.
- PAYLOAD_S3_SECRET_ACCESS_KEY: The secret access key for S3-compatible storage.
- PAYLOAD_S3_FORCE_PATH_STYLE: Set to true for compatible S3-style endpoints.

## Database Setup

1. Create a Supabase project.
2. Open Project Settings > Database and copy the PostgreSQL Transaction Pooler connection string.
3. Set PAYLOAD_DATABASE_URI to that value. You can also set DATABASE_URL to the same value.
4. Generate a strong PAYLOAD_SECRET and set it in your environment.
5. Set NEXT_PUBLIC_SITE_URL to your public site URL, such as http://localhost:3000 for local development.
6. Configure Payload media storage by setting the S3 variables if you want to use S3-compatible storage. Otherwise the project can use the local upload directory under public/payload-media.

### PAYLOAD_DATABASE_URI vs DATABASE_URL

- PAYLOAD_DATABASE_URI is the primary connection string for the Payload/Postgres adapter.
- DATABASE_URL is an additional alias used by the application and seed workflow.
- In most setups, both should point to the same PostgreSQL database.

## Payload CMS

The project ships with a dedicated Payload admin experience at /cms.

### Development

- Website: http://localhost:3000
- CMS: http://localhost:3000/cms

### Production

- Website: https://YOUR_DOMAIN
- CMS: https://YOUR_DOMAIN/cms

Once signed in, you can:

- Create portfolio categories
- Upload images
- Create portfolio projects
- Edit the homepage
- Change branding
- Edit the owner profile
- Manage navigation and footer
- Change theme colours
- Edit SEO
- Manage testimonials
- Manage FAQs

Almost every visible section of the site is editable through Payload CMS, so normal content updates do not require source code changes.

## Customization

You can customize the site by updating CMS content directly:

- Replace branding and logo assets
- Change colours and theme presets
- Replace hero and portfolio images
- Rename categories
- Update owner information
- Edit homepage content and SEO
- Upload creative work and manage media
- Extend Payload collections and globals when you need additional content models

No code changes are required for everyday content management.

## Commands

The repository includes the following npm scripts:

- npm run dev: Start the Next.js development server.
- npm run build: Create a production build.
- npm run start: Start the production build locally.
- npm run lint: Run ESLint.
- npm run payload: Start the Payload CLI.
- npm run payload:generate-importmap: Generate the Payload import map.
- npm run payload:generate-types: Generate TypeScript types from the Payload schema.
- npm run payload:migrate: Run Payload migrations.
- npm run payload:seed: Seed starter content into Payload collections and globals.

### Payload migration workflow

```bash
npm run payload:generate-types
npm run payload:migrate
```

If you want to populate the CMS with starter content, run:

```bash
npm run payload:seed
```

## Deployment

The app is designed for deployment to Vercel.

### Required environment variables

Set the following variables in your deployment environment:

- PAYLOAD_SECRET
- PAYLOAD_DATABASE_URI
- DATABASE_URL
- NEXT_PUBLIC_SITE_URL
- NEXT_PUBLIC_SUPABASE_URL
- NEXT_PUBLIC_SUPABASE_ANON_KEY
- SUPABASE_SERVICE_ROLE_KEY
- NEXT_PUBLIC_SUPABASE_MEDIA_BUCKET
- PAYLOAD_S3_BUCKET
- PAYLOAD_S3_REGION
- PAYLOAD_S3_ENDPOINT
- PAYLOAD_S3_ACCESS_KEY_ID
- PAYLOAD_S3_SECRET_ACCESS_KEY
- PAYLOAD_S3_FORCE_PATH_STYLE

### Production checklist

- Configure the production database connection strings.
- Set a strong PAYLOAD_SECRET.
- Set the production NEXT_PUBLIC_SITE_URL.
- Configure Supabase auth and storage.
- Configure S3-compatible storage if you want remote Payload media storage.
- Run the Payload migration workflow before the first production deploy.

## Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push the branch.
5. Open a pull request.

## Security

Keep local secrets out of version control.

Never commit:

- .env.local
- Database credentials
- Payload secrets
- Supabase service role keys
- S3 secret keys

Use [.env.example](.env.example) as the template for new local configuration.

## FAQ

### How do I access the CMS?

Open http://localhost:3000/cms during development or https://YOUR_DOMAIN/cms in production.

### How do I create the first administrator?

Create a Supabase auth user and set the matching record in public.users to role 'admin'.

### How do I add portfolio items?

Sign in to the CMS, open the Portfolio manager, and create categories and portfolio entries.

### How do I upload media?

Use the Media manager in the CMS to upload images. If S3 variables are configured, Payload can store media in S3-compatible storage.

### How do I edit theme colours?

Open Theme Settings in the CMS and adjust the preset, colour values, and visual controls.

### How do I deploy?

Deploy to Vercel with the environment variables configured and run the Payload migration workflow before launch.

## Roadmap

There is no formal roadmap file in the repository at this time. The current focus is on polished CMS-driven publishing, admin workflows, deployment readiness, and extensible content models for image-based creative portfolios.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Support

- GitHub Issues: https://github.com/ancientwebofficial/Creative-studio/issues
- GitHub Discussions: https://github.com/ancientwebofficial/Creative-studio/discussions
