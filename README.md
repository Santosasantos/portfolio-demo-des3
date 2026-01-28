# Professional Portfolio Website

A modern, full-featured portfolio website built with Next.js and Supabase. This professional portfolio showcases academic achievements, research publications, work experience, skills, and provides an intuitive admin panel for content management. Currently configured with seed data for **Rifat Ahmed - Software Engineer & Research Enthusiast**.

## 🌟 Features

### Public-Facing Features
- **Dynamic Portfolio Pages**: Beautiful, responsive pages showcasing:
  - Academic publications (peer-reviewed articles, conference papers with images, PDFs, and videos)
  - Education history
  - Professional experience (Research & Industry)
  - Skills & certifications (with country flag images for languages)
  - Awards & achievements (with certificate images)
  - Volunteering activities
  - Scholarly activities
  - Contact form with email notifications
  - Dynamic footer with profile information

### Admin Panel
- **Secure Authentication**: Protected admin dashboard with role-based access
- **Content Management System**: Easy-to-use interface for managing all portfolio content
- **Media Management**: Upload and manage images, PDFs, and conference materials
- **Real-time Updates**: Content changes reflect immediately with automatic cache revalidation
- **CRUD Operations**: Create, read, update, and delete all portfolio sections

### Technical Features
- **Server-Side Rendering**: Optimized performance with Next.js Server Components
- **Database Integration**: Powered by Supabase for scalable data management
- **File Storage**: Secure file uploads with Supabase Storage (images, PDFs, videos)
- **Email Integration**: Contact form submissions via Resend API
- **SEO Optimized**: Meta tags, structured data, and semantic HTML
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Language Flags**: Country flag images for language skills display
- **Dynamic Content**: Profile data fetched dynamically from database

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 16 (App Router)
- **UI Library**: React 19
- **Styling**: Tailwind CSS 4
- **UI Components**: Radix UI
- **Icons**: Lucide React
- **Forms**: React Hook Form + Zod validation

### Backend & Database
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth
- **File Storage**: Supabase Storage
- **Email Service**: Resend API

### Development
- **Language**: TypeScript
- **Package Manager**: npm
- **Deployment**: Vercel

## 📋 Prerequisites

Before running this project, ensure you have:

- Node.js 18+ installed
- npm or yarn package manager
- Supabase account (for database and storage)
- Resend API key (for email functionality)
- Git (for version control)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd portfolio-db-amir-main
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Variables

Create a `.env.local` file in the root directory:

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
RESEND_API_KEY=your_resend_api_key
```

### 4. Database Setup

#### Option A: New Supabase Project (Recommended)

For a fresh setup, use the complete setup script:

1. Create a new Supabase project at [supabase.com](https://supabase.com)
2. Open SQL Editor in Supabase Dashboard
3. Run `scripts/000_COMPLETE_SETUP_FROM_SCRATCH.sql` - Complete database setup (tables, storage, policies)
4. Run `scripts/014_seed_bangladeshi_profile.sql` - Insert seed data for Rifat Ahmed profile

**See `scripts/SETUP_FROM_SCRATCH.md` for detailed step-by-step instructions.**

#### Option B: Existing Project

If you have an existing project, run scripts in order:
- `001_create_tables.sql` - Creates all necessary tables
- `003_create_storage_bucket.sql` - Sets up file storage
- `015_ensure_storage_setup.sql` - Ensures all storage buckets and columns exist
- `014_seed_bangladeshi_profile.sql` - Insert seed data

### 5. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### 6. Build for Production

```bash
npm run build
npm start
```

## 📁 Project Structure

```
portfolio-project-first-order/
├── app/                    # Next.js App Router pages
│   ├── admin/             # Admin panel routes
│   ├── api/               # API routes
│   ├── auth/              # Authentication pages
│   └── [pages]/           # Public-facing pages
├── components/            # React components
│   ├── ui/               # Reusable UI components
│   └── [feature]/        # Feature-specific components
├── lib/                   # Utility functions
│   └── supabase/         # Supabase client configuration
├── scripts/              # Database migration scripts
│   ├── 000_COMPLETE_SETUP_FROM_SCRATCH.sql  # Complete setup for new projects
│   ├── 014_seed_bangladeshi_profile.sql     # Seed data (Rifat Ahmed)
│   ├── 015_ensure_storage_setup.sql         # Storage configuration
│   └── *.md              # Setup documentation
├── public/               # Static assets
└── proxy.ts              # Next.js proxy middleware
```

## 🔐 Authentication

The admin panel is protected by Supabase Authentication. To access:

1. Navigate to `/auth/login`
2. Use your admin credentials
3. All admin routes are automatically protected

## 📝 Content Management

All content can be managed through the admin panel at `/admin`. The system supports:

- **Publications**: Academic papers, conference presentations (with images, PDFs, videos), work in progress
- **Education**: Academic degrees and certifications
- **Experience**: Research and industry positions
- **Skills**: Categorized skills with proficiency levels (language skills display country flags)
- **Awards**: Academic and professional recognitions (with certificate images)
- **Certifications**: Professional certifications with credentials
- **Volunteering**: Community service activities
- **Scholarly Activities**: Academic service and contributions
- **Profile**: Personal information, contact details, social links

## 🚢 Deployment

This project is optimized for deployment on Vercel:

1. Push your code to GitHub
2. Import the repository in Vercel
3. Add environment variables in Vercel dashboard
4. Deploy automatically on every push

### Environment Variables for Production

Ensure all environment variables from `.env.local` are added to your Vercel project settings.

## 🔧 Key Features Implementation

### Cache Management
- Dynamic rendering enabled for real-time content updates
- Automatic cache revalidation on content changes
- Optimized for production performance

### File Uploads
- **Profile Images**: Profile photos stored in `profile-images` bucket
- **Award Images**: Certificate images in `award-images` bucket
- **Conference Images**: Presentation photos in `conference-images` bucket
- **Academic PDFs**: Research papers in `academic-pdfs` bucket
- **Conference PDFs**: Conference papers in `conference-pdfs` bucket
- **Conference Videos**: Presentation videos in `conference-videos` bucket
- Secure file storage with Supabase Storage

### Email Notifications
- Contact form submissions sent via Resend
- Automatic email notifications for admin

## 📚 Documentation

### Setup Guides
- **New Project Setup**: See `scripts/SETUP_FROM_SCRATCH.md` - Complete guide for fresh Supabase projects
- **Quick Start**: See `scripts/QUICK_START.md` - Fast setup instructions
- **Setup Checklist**: See `scripts/CHECKLIST_NEW_PROJECT.md` - Step-by-step checklist
- **Seed Data Guide**: See `scripts/README_BANGLADESHI_SEED.md` - Complete seed data documentation

### Configuration
- **Authentication Setup**: See `AUTHENTICATION_FIX.md`
- **Email Configuration**: See `EMAIL_SETUP.md`
- **Profile Image Guide**: See `scripts/018_ADD_PROFILE_IMAGE.md` - How to add profile photos
- **Database Schema**: Check SQL scripts in `scripts/` directory

### Seed Data
The project includes complete seed data for **Rifat Ahmed** - a Bangladeshi Software Engineer profile with:
- 3 Education records (BUET, Notre Dame College, Motijheel Ideal School)
- 5 Experience records (bKash, Grameenphone, BUET, Freelance)
- 5 Publications (with conference images, PDFs, videos)
- 16 Skills (including Bengali 🇧🇩 and English 🇬🇧 with flag images)
- 4 Awards (with image URLs)
- 5 Volunteering activities
- 5 Scholarly activities
- 7 Certifications

## 🎨 Customization

### Changing Profile Data

1. **Update Seed Data**: Modify `scripts/014_seed_bangladeshi_profile.sql` with your information
2. **Update Profile Image**: Follow `scripts/018_ADD_PROFILE_IMAGE.md` to add your photo
3. **Update Media URLs**: Use `scripts/017_update_media_urls.sql` after uploading files
4. **Update Page Title**: Modify `app/layout.tsx` metadata

### Adding New Languages

To add new language skills with flags:
1. Add the language to the database via admin panel
2. Add flag mapping in `app/page.tsx` and `app/skills/page.tsx`:
   ```typescript
   const languageFlags: Record<string, string> = {
     // ... existing flags
     YourLanguage: "https://flagcdn.com/w320/xx.png", // Replace xx with country code
   }
   ```

## 🔄 Database Migration

### For New Projects
Run `scripts/000_COMPLETE_SETUP_FROM_SCRATCH.sql` - This single script sets up everything.

### For Existing Projects
Run scripts in order:
1. `001_create_tables.sql` - Create tables
2. `015_ensure_storage_setup.sql` - Setup storage
3. `014_seed_bangladeshi_profile.sql` - Insert data

## 🤝 Support

For questions or support regarding this project:
- Check the documentation in `scripts/` directory
- Review setup guides for common issues
- Check Supabase logs for database errors

## 📄 License

This project is proprietary and confidential. All rights reserved.

---

