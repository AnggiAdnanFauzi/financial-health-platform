# Enterprise Financial Health Diagnostic Platform

A modern, full-stack application for assessing personal and corporate financial health. Built with a decoupled architecture featuring a React SPA frontend and a robust Laravel REST API backend.

## 🚀 Tech Stack

**Frontend:**
- React (Vite)
- TypeScript
- Tailwind CSS (Premium UI/UX)
- Lucide Icons & Framer Motion

**Backend:**
- Laravel 11.x (PHP 8.2+)
- MySQL (Cloud Database via Aiven)
- Cloudinary (Image & Asset CDN)

---

## 🛠️ Installation & Local Setup

Follow these steps to run the project locally on your machine.

### 1. Backend (Laravel) Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Install PHP dependencies via Composer:
   ```bash
   composer install
   ```
3. Setup Environment Variables:
   - Duplicate `.env.example` and rename it to `.env`
   - Create your own MySQL Database (e.g., via Aiven or local XAMPP) and Cloudinary account.
   - Fill in the respective credentials and API keys in your new `.env` file.
4. Generate the Application Key:
   ```bash
   php artisan key:generate
   ```
5. Run Migrations & Seeders:
   *(This will automatically create the database tables and inject the default Super Admin account)*
   ```bash
   php artisan migrate --seed
   ```
6. Start the Laravel Development Server:
   ```bash
   php artisan serve
   ```
   *The backend API will run on http://localhost:8000*

### 2. Frontend (React) Setup

1. Open a new terminal and navigate to the project root directory.
2. Install Node.js dependencies:
   ```bash
   npm install
   ```
3. Setup Environment Variables:
   - Create a `.env` file in the root directory.
   - If required (e.g., Gemini API), create your own API key and add it to the `.env` file.
4. Start the Vite Development Server:
   ```bash
   npm run dev
   ```
   *The frontend will run on http://localhost:3000 (or another port specified by Vite)*

---

## 🔐 Default Admin Account

After running `php artisan migrate --seed`, you can log in to the Admin Panel using the following credentials:

- **Email:** `admin@financialhealth.com`
- **Password:** `admin123`

---

## ☁️ Deployment Notes

- The Frontend is optimized for Vercel deployment (SPA routing fallback is configured via `vercel.json`).
- The Backend requires a PHP-compatible hosting environment (e.g., Vercel PHP, Heroku, Render, or a VPS).
