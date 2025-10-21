
# 🌐 MARKETER LINK MANAGER — Built with Cloud AI (no database)

Create a web-based UTM link manager for marketers, campaign managers, and growth teams. This should behave like an editable spreadsheet (similar to Clay or AirOps), powered entirely by Lovable Cloud AI — no external database needed.

---

## 🧠 FEATURES & UX

### 🎯 Goal:
Let users easily:
- Paste original URLs
- Create editable aliases and campaign metadata
- Auto-generate a shortened URL
- Compose full UTM URLs
- Track click analytics
- Export/download table
- Add dynamic fields and rows
- Create QR codes from shortened URLs (optional, Phase 2)

---

## ✍️ Table UI

Create an editable, responsive table with the following columns:

```plaintext
- Original URL (input field)
- Campaign Name (editable text)
- Alias (Path) → auto-suggested if blank
- UTM Content
- UTM Source
- UTM Medium
- UTM Campaign
- Shortened URL → auto-generated from Alias
- Full UTM URL → auto-generated using all fields
- Notes
- Clicks → tracked per short URL
```

- Users can add new rows or columns at will (make table dynamic).
- Allow drag-to-reorder rows if possible.

---

## 🧠 CLOUD AI LOGIC

1. When a user enters a new Original URL:
   - Auto-generate a slug from the title or URL (e.g., `/demo-video`)
   - Auto-populate the alias if left blank
   - Auto-create a shortened URL: `https://yourbrand.io/demo-video`
   - Combine UTM fields to produce:  
     `https://original.com?utm_source=...&utm_medium=...&utm_campaign=...`

2. Full UTM URL field should update live as any of the UTM fields are edited.

3. "Clicks" column should simulate click tracking (for MVP), or include placeholder logic that could integrate with real tracking in Phase 2.

---

## 📈 ANALYTICS DASHBOARD PAGE

Create a simple dashboard view that visualizes:

- Total links created
- Total clicks (sum of all rows) over time line chart
- Clicks by referrer (UTM Source)
- Bar chart: Clicks per Campaign
- Bar chart: Distribution by UTM Source
- Filter by campaign name, date created, or UTM source, medium, campaign

Use a `dashboard()` component placed above the table.

---

## 📤 EXPORT / DOWNLOAD

- Include a **"Download CSV"** button that allows the user to export the current table (with all fields and rows)
- Add a "Copy table to clipboard" button
- Allow import/upload of CSV to pre-fill rows

---

## 🧩 EXTRA FUNCTIONALITY

- Enable "+" buttons for users to dynamically add rows or columns.
- Make it mobile-friendly with responsive wrapping.
- Optional: Save table state per user (via Lovable's built-in cloud memory).

---

## ✨ DESIGN & UX STYLE

- Use modern, clean UI (like AirOps or Clay)
- Hover states, light borders, subtle highlights
- CTA color: `#FFC400` (golden yellow)
- Title the app: **“Smart UTM Link Manager”**

---

## 🔗 Example Output Row

```plaintext
Original URL: https://example.com/product-launch
Campaign Name: Oct Product Push
Alias: product-launch
UTM Source: linkedin
UTM Medium: post
UTM Campaign: oct_launch
Shortened URL: https://yourbrand.io/product-launch
Full UTM URL: https://example.com/product-launch?utm_source=linkedin&utm_medium=post&utm_campaign=oct_launch
Clicks: 128
Notes: Used in LinkedIn teaser
```

---

## 📌 Instructions for Lovable

Use Cloud AI to manage state, generate fields, and perform transformations. No Supabase or external DB needed.

Name the app: `Best UTM Link Manager`.
