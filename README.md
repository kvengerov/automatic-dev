# Automatic Dev

A modern Next.js application built with TypeScript, Prisma, and PostgreSQL.

## Tech Stack

- **Framework**: [Next.js 15](https://nextjs.org) with App Router
- **Language**: TypeScript
- **Database**: PostgreSQL with [Prisma ORM](https://www.prisma.io)
- **UI Components**: [Radix UI](https://www.radix-ui.com)
- **Styling**: [Tailwind CSS](https://tailwindcss.com)
- **Code Quality**: [Biome](https://biomejs.dev)
- **Form Handling**: React Hook Form with Zod validation

## Getting Started

### Prerequisites

- Node.js 20+
- PostgreSQL database
- npm, yarn, pnpm, or bun

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd automatic-dev
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
cp .env.example .env
```

Edit `.env` and add your database connection string:
```env
DATABASE_URL="postgresql://user:password@localhost:5432/database_name?schema=public"
```

4. Run database migrations:
```bash
npx prisma migrate dev
```

5. Generate Prisma Client:
```bash
npx prisma generate
```

6. Start the development server:
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Scripts

- `npm run dev` - Start development server with Turbopack
- `npm run build` - Build for production with Turbopack
- `npm run start` - Start production server
- `npm run lint` - Run Biome linter
- `npm run format` - Format code with Biome

## Database

This project uses Prisma ORM for database management.

### Prisma Commands

- `npx prisma migrate dev` - Create and apply migrations in development
- `npx prisma migrate deploy` - Apply migrations in production
- `npx prisma generate` - Generate Prisma Client
- `npx prisma studio` - Open Prisma Studio (database GUI)
- `npx prisma db push` - Push schema changes without migrations

### Database Schema

The current schema includes:
- **User** - User accounts with authentication
- **Post** - Blog posts with author relationship

See `prisma/schema.prisma` for the complete schema definition.

## Project Structure

```
├── prisma/
│   ├── schema.prisma          # Database schema
│   └── migrations/            # Database migrations
├── src/
│   ├── app/                   # Next.js app router pages
│   ├── components/            # React components
│   │   └── ui/               # UI component library
│   ├── generated/            # Generated Prisma Client
│   ├── hooks/                # Custom React hooks
│   └── lib/                  # Utility functions and db client
└── public/                   # Static assets
```

## Environment Variables

Required environment variables:
- `DATABASE_URL` - PostgreSQL connection string

## Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Radix UI Documentation](https://www.radix-ui.com/docs)

## Deploy on Vercel

The easiest way to deploy is using the [Vercel Platform](https://vercel.com/new).

Make sure to set the `DATABASE_URL` environment variable in your Vercel project settings.
