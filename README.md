
# 🕊️ Whistle – Anonymous Reporting App

Whistle is a privacy-focused, anonymous reporting web application built for large public events like hackathons. It allows participants to report incidents safely, optionally attach photo proof, and notify the safety team in real-time — without revealing their identity.

---

## 🌐 Live Demo
> Coming soon...

---

## 🚀 Features

- 🧍‍♂️ **Anonymous Reporting** with optional photo uploads
- 🧑‍💼 **Admin Dashboard** to manage and review reports
- 🛡️ **End-to-end Privacy** with role-based access
- 🔔 **Real-time Alerts** using GraphQL subscriptions
- 🖼️ **Photo Proof Uploads** with secure access

---

## 🧱 Tech Stack

| Layer       | Technology              |
|-------------|--------------------------|
| Frontend    | [Next.js](https://nextjs.org), [Tailwind CSS](https://tailwindcss.com) |
| Backend     | [Nhost](https://nhost.io) (PostgreSQL + Hasura) |
| Auth        | Nhost Auth (Anonymous Sessions & Admin Roles) |
| Realtime    | Hasura Subscriptions (GraphQL) |
| Storage     | Nhost Storage (private file uploads) |
| Deployment  | Vercel (Frontend) + Nhost Cloud |

---

## 📦 Installation

### 1. Clone the repository
```bash
git clone https://github.com/your-username/whistle.git
cd whistle
````

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env.local` file:

```env
NEXT_PUBLIC_NHOST_SUBDOMAIN=your-nhost-subdomain
NEXT_PUBLIC_NHOST_REGION=your-nhost-region
```

### 4. Run the dev server

```bash
npm run dev
```

---

## 📁 Project Structure

```
whistle/
├── pages/
│   ├── index.tsx         # Landing page
│   ├── report.tsx        # Anonymous report form
│   ├── admin.tsx         # Admin dashboard
├── components/           # Reusable UI components
├── graphql/              # GraphQL queries and mutations
├── utils/
│   └── nhost.ts          # Nhost client config
├── styles/               # Tailwind/global CSS
```

---

## 📊 Database Schema (via Hasura)

### reports

| Field       | Type      | Description              |
| ----------- | --------- | ------------------------ |
| id          | UUID      | Primary key              |
| message     | Text      | Report content           |
| photo\_url  | Text      | Optional photo proof URL |
| status      | Text      | `pending` or `reviewed`  |
| created\_at | Timestamp | Auto-set                 |

### admin\_responses (optional)

| Field       | Type      | Description              |
| ----------- | --------- | ------------------------ |
| id          | UUID      | Primary key              |
| report\_id  | UUID      | Foreign key to `reports` |
| response    | Text      | Admin message            |
| created\_at | Timestamp | Auto-set                 |

---

## 🔐 Permissions (Hasura Roles)

### anonymous\_user

* ✅ Can insert into `reports`
* ❌ Cannot read, update, or delete

### admin

* ✅ Can read, update, delete reports
* ✅ Full access to admin dashboard

---

## 🧠 Possible Enhancements

* 🌈 Dark mode toggle
* 🧾 Download report as PDF
* 🔊 Admin notification sound
* 📲 PWA support (for offline-ready usage)

---

## 🧑‍💻 Contributing

Contributions are welcome! Open an issue or submit a PR.

---

## 📜 License

MIT License © 2025 Ritika S

---

## 📬 Contact

Built with ❤️ by [Ritika S](https://github.com/Esdeath4l)
Have suggestions or ideas? Drop them in the issues tab!
