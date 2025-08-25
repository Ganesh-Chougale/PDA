## **Phase 1: Core Project Setup & Skeleton**

1.1 Initialize Next.js project with pages/app structure.
1.2 Setup TailwindCSS + basic theme.
1.3 Setup Node + Express server skeleton.
1.4 Configure MySQL connection (Prisma/Sequelize optional).
1.5 Setup `.env` for DB credentials & API keys.
1.6 Setup Git repo and initial commit.

---

## **Phase 2: User Authentication**

2.1 Add `users` table in MySQL.
2.2 Implement registration & login APIs.
2.3 Add password hashing (bcrypt).
2.4 Implement JWT authentication.
2.5 Frontend login & registration forms integrated with backend.
2.6 State management for user authentication (Context API/Zustand).

---

## **Phase 3: Basic Data Models & Seeding**

3.1 Create tables: Individuals, Events, Tags.
3.2 Define relationships:

* Individual → Events (1\:N)
* Individual → Tags (M\:N)
  3.3 Seed dummy data for testing.
  3.4 Test backend APIs with Postman/Insomnia.

---

## **Phase 4: Backend API – CRUD for Entries & Events**

4.1 CRUD APIs for Individuals/Entries.
4.2 CRUD APIs for Events ("knots").
4.3 API endpoint to fetch an individual with nested events.
4.4 Input validation & error handling.

---

## **Phase 5: Frontend – Display & Basic Visualization**

5.1 Display list of Individuals with categories.
5.2 Individual detail page showing events in a simple vertical timeline.
5.3 Integrate Visx for vertical rope structure.
5.4 Tooltip/modal to show event details.
5.5 Test frontend fetching from backend API.

---

## **Phase 6: Event Media & Forms**

6.1 Add forms to create/update Individuals and Events.
6.2 Implement file/media upload API (local or Cloudinary).
6.3 Link uploaded media to events.
6.4 Display media in modals or expandable cards.
6.5 Ensure responsive layout for media-heavy entries.

---

## **Phase 7: Tagging System**

7.1 Create `tags` and `tag_types` tables, and M\:N join table.
7.2 Backend APIs to create, attach, and manage tags.
7.3 Frontend component for adding/displaying tags.
7.4 Implement basic tag searching & filtering (+ inclusion, - exclusion).
7.5 Moderation: report/review/approve tags/events.

---

## **Phase 8: Categories, Filters & Search**

8.1 Implement category tabs: People, Business, Things, Animals, Ideology.
8.2 Filter Individuals/Entries by type (real, fictional, mythological).
8.3 Implement robust backend search API (keywords, tags, categories).
8.4 Frontend search page with filters and tag inclusion/exclusion.
8.5 Test search & filtering performance.

---

## **Phase 9: Comparison Mode**

9.1 Backend API to fetch multiple entries and their events.
9.2 Frontend page for comparison mode (side-by-side ropes).
9.3 Synchronize time axis across ropes.
9.4 Highlight overlapping periods/events.
9.5 Add zoom/pan for large timelines.

---

## **Phase 10: User Profiles & Social Features**

10.1 User profile page showing contributions (created entries/events).
10.2 "Favorite" or "like" functionality for Danglers.
10.3 "My favorites" list for logged-in users.
10.4 Comment system for events/entries with backend APIs.
10.5 Display comments under each entry with moderation options.

---

## **Phase 11: UI/UX Enhancements & Animations**

11.1 Smooth animations for rope growth, knots, and hover effects (Framer Motion).
11.2 Dark/light theme toggle.
11.3 Responsive design for mobile/tablet.
11.4 Polished comparison highlights & media display.
11.5 Minor micro-interactions (tooltips, modals, buttons).

---

## **Phase 12: Performance, Testing & Deployment**

12.1 Optimize backend queries for search and comparison.
12.2 Implement caching if needed (Redis).
12.3 Pagination for large datasets.
12.4 Full testing: search, tags, media, comparison, auth, comments.
12.5 Deploy frontend (Vercel/Netlify) and backend (Railway/Heroku).
12.6 GitHub version tagging & milestone tagging for each phase.

---

This plan gives you:

* **Small, achievable pushes** → every phase can be a Git milestone.
* **Full feature set** → visualization, comparison, tagging, community, search.
* **Future-ready** → easy to expand features like analytics, recommendations, or AI-powered suggestions.

---