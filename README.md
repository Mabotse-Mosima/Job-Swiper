# JobSwipers

JobSwipers is a swipe-based job-matching platform designed to connect job seekers with employment opportunities. Users can browse job listings and swipe right to express interest or swipe left to pass. Notifications are triggered only when a user shows interest (swipes right).

## 🔧 Features

- 👤 **User Dashboard** with personalized greeting and job suggestions.
- 📄 **Dynamic Job Listings** pulled from a MySQL database.
- 🖼️ Company logos automatically displayed from the `uploads/` folder or fall back to `default_logo.png`.
- 👆 Swipe left/right using [Hammer.js](https://hammerjs.github.io/) for mobile-like interaction.
- 🔔 **Notifications** inserted into the database only when the user swipes right (shows interest).
- 📬 Notification message: _"You have shown interest in job ID X"_.
- 🔒 Profile dropdown with options to view profile, review companies, or sign out.
- 💻 Built using PHP, MySQL, HTML, CSS, and JavaScript (Hammer.js).

## 💡 How It Works

1. **Jobs Table**: Jobs are fetched from the database, optionally joined with company logos.
2. **Swiping**: Implemented using `Hammer.js`, users swipe right to "like" and left to "skip".
3. **Notification Logic**: On a right swipe, a new record is inserted into the `notifications` table.
4. **Visuals**: Each job is presented as a card with logo, title, location, and salary info.

## 🛠️ Technologies Used

- PHP 8.x
- MySQL 5.7+
- HTML5/CSS3
- JavaScript (Vanilla + Hammer.js)
- XAMPP/WAMP or LAMP recommended for local development

## 🗃️ Database Structure

### `jobs` Table

| Column        | Type         |
|---------------|--------------|
| id            | INT (PK)     |
| job_title     | VARCHAR      |
| job_description | TEXT       |
| job_location  | VARCHAR      |
| job_type      | VARCHAR      |
| company_name  | VARCHAR      |
| salary        | VARCHAR      |
| created_at    | TIMESTAMP    |

### `notifications` Table

| Column      | Type         |
|-------------|--------------|
| id          | INT (PK)     |
| user_id     | INT (FK)     |
| job_id      | INT (FK)     |
| message     | VARCHAR(255) |
| created_at  | TIMESTAMP    |

## 🖼️ Images

- Company logos are stored under `/uploads/`.
- If no logo is provided, `default_logo.png` is shown.

## 📁 File Structure

