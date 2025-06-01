## 🚀 Project Overview

This project consists of two main components:
- **Frontend**: Next.js 14+ with App Router, Tailwind CSS, and shadcn/ui components
- **Backend**: Django REST API (BFF - Backend for Frontend) with SQLite database
- **Static Assets**: Video thumbnails and channel avatars

## 📋 Features

### ✅ Implemented Features
- **Video Player**: Interactive player with YouTube-style controls, progress bar, and overlay effects
- **Video Details**: Title, channel info, action buttons (like, share, download, save), description
- **Comments Section**: Comment count and sort functionality
- **Video Recommendations**: Right sidebar with video thumbnails, duration badges, and metadata
- **Responsive Design**: Mobile, tablet, and desktop layouts
- **Category Filters**: Main content categories and sub-categories
- **Search Functionality**: Search bar with API integration
- **Dynamic Data**: Real video data served from Django API

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 14+ with App Router
- **Styling**: Tailwind CSS v4
- **UI Components**: shadcn/ui with Radix UI primitives
- **Icons**: Lucide React
- **Language**: JavaScript (ES6+)

### Backend
- **Framework**: Django 4.2+
- **API**: Django REST Framework
- **Database**: SQLite (development)
- **CORS**: django-cors-headers
- **Image Handling**: Pillow

## 📁 Project Structure 
Youtube Homepage/
├── frontend/ # Next.js frontend application
│ ├── src/
│ │ ├── app/ # Next.js App Router pages
│ │ ├── components/ # React components
│ │ │ ├── layout/ # Layout components (Header, MainContent)
│ │ │ ├── video/ # Video-related components
│ │ │ ├── common/ # Shared components
│ │ │ └── ui/ # shadcn/ui components
│ │ ├── hooks/ # Custom React hooks
│ │ └── lib/ # Utility functions and API helpers
│ ├── public/ # Static assets
│ └── package.json
├── backend/ # Django backend application
│ └── youtube_api/
│ ├── api/ # Django app for API endpoints
│ ├── youtube_bff/ # Django project settings
│ ├── manage.py
│ └── db.sqlite3
├── static/ # Shared static assets
│ ├── thumbnails/ # Video thumbnail images
│ └── avatars/ # Channel avatar images
└── README.md

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18+ and npm
- **Python** 3.8+ and pip
- **Git**

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd "Youtube Homepage"
```

### 2. Backend Setup (Django)

```bash
# Navigate to backend directory
cd backend/youtube_api

# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install Python dependencies
pip install -r ../requirements.txt

# Run database migrations
python manage.py migrate

# Seed the database with sample data
python manage.py seed_data

# Start Django development server
python manage.py runserver
```

The Django API will be available at `http://localhost:8000`

### 3. Frontend Setup (Next.js)

```bash
# Navigate to frontend directory (from root)
cd frontend

# Install Node.js dependencies
npm install

# Start Next.js development server
npm run dev
```

The frontend will be available at `http://localhost:3000`

### 4. Verify Setup

1. **Backend API**: Visit `http://localhost:8000/api/getvideos/` - should return JSON video data
2. **Frontend**: Visit `http://localhost:3000` - should show the YouTube clone interface

## 🔧 Development Workflow

### Starting Both Servers Simultaneously

The frontend includes scripts to run both backend and frontend together:

```bash
cd frontend

# Run both servers concurrently
npm run dev:full
```

This command will start both Django (`http://localhost:8000`) and Next.js (`http://localhost:3000`) servers simultaneously.

### Individual Commands

**Backend Commands:**
```bash
cd frontend

# Run migrations
npm run backend:migrate

# Seed database
npm run backend:seed

# Setup backend (migrate + seed)
npm run backend:setup

# Start Django server
npm run backend:dev
```

**Frontend Commands:**
```bash
cd frontend

# Development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Lint code
npm run lint
```

## 📊 API Endpoints

The Django backend provides the following API endpoints:

### Videos
- `GET /api/getvideos/` - Get list of videos for homepage
- `GET /api/getvideodata/<id>/` - Get specific video details

### Categories
- `GET /api/getcategories/` - Get video categories
- `GET /api/getsubcategories/` - Get video sub-categories

### Static Files
- `/static/thumbnails/<filename>` - Video thumbnail images
- `/static/avatars/<filename>` - Channel avatar images

## 🎯 Key Components

### Frontend Components

**Layout Components:**
- `Header.js` - Navigation header with search functionality
- `MainContent.js` - Main layout container with responsive design

**Video Components:**
- `VideoPlayer.js` - Interactive video player with controls
- `VideoDetails.js` - Video metadata, channel info, action buttons
- `VideoRecommendations.js` - Sidebar with recommended videos
- `CategoryChips.js` - Category filter chips

**Common Components:**
- `Logo.js` - YouTube logo component
- `UserMenu.js` - User profile dropdown
- `SafeImage.js` - Image component with fallbacks

### Backend Models

**Video Model:**
- Title, description, duration, views, upload date
- Channel information (name, subscribers, avatar)
- Thumbnail images and metadata

**Category Models:**
- Main categories (All, Comedy, Education, Gaming, Live)
- Sub-categories with filtering capabilities

## 🎨 Styling Guidelines

The project uses Tailwind CSS with YouTube-accurate styling:

- **Colors**: YouTube red (`#ff0000`), grays for text and backgrounds
- **Typography**: Roboto-like font stack with specific font sizes
- **Spacing**: Consistent padding and margins matching YouTube
- **Responsive**: Mobile-first approach with breakpoints at sm, md, lg, xl, 2xl

## 🔧 Configuration

### Environment Variables

Create `.env.local` in the frontend directory if needed:

```env
NEXT_PUBLIC_API_URL=http://localhost:8000
```

### Port Conflicts

If default ports are occupied:

**Backend (Django):**
```bash
python manage.py runserver 8001
```

**Frontend (Next.js):**
```bash
npm run dev -- -p 3001
```

Update CORS settings in Django accordingly.

## 📱 Responsive Design

The application is fully responsive with breakpoints:

- **Mobile** (< 768px): Single column layout, stacked content
- **Tablet** (768px - 1024px): Optimized spacing and components
- **Desktop** (> 1024px): Two-column layout with video player and recommendations sidebar

## 🚀 Deployment

### Frontend (Vercel/Netlify)

```bash
cd frontend
npm run build
npm start
```

## 📄 License

This project is for educational purposes only. YouTube is a trademark of Google LLC.

## 👥 Authors

- Mynul Islam