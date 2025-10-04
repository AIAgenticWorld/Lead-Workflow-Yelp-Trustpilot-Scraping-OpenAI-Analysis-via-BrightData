<img width="708" height="408" alt="image" src="https://github.com/user-attachments/assets/7bf01f53-c380-41a5-be86-c1712e6eb026" />
# 🔍 AI-Powered Lead Generation Workflow

This automated lead generation workflow identifies high-quality business prospects from Yelp and Trustpilot, verifies their credibility, and sends personalized outreach emails using AI. Built with **n8n**, this solution is ideal for digital marketing agencies, sales teams, and business development professionals.

---

## ✨ Key Features

- 🎯 **Smart Location Analysis** — Gemini AI breaks down cities into sub-locations for thorough coverage.
- 🛍 **Yelp Integration** — Extracts business details via BrightData’s Yelp dataset.
- ⭐ **Trustpilot Verification** — Scrapes and analyzes reviews to determine business credibility.
- 📊 **Data Storage** — Stores lead data in connected Google Sheets.
- 🤖 **AI-Powered Outreach** — Claude AI generates customized email messages.
- 📧 **Automated Sending** — Emails sent directly via Gmail integration.

---

## 🔄 How It Works

1. **User Input** — Submit location, country, and business category via form.
2. **AI Location Analysis** — Gemini AI breaks the area into granular sub-locations.
3. **Yelp Scraping** — BrightData extracts business info.
4. **Data Processing** — Info is cleaned and stored in Google Sheets.
5. **Trustpilot Verification** — Scrapes credibility/review data.
6. **Email Generation** — Claude AI drafts personalized emails.
7. **Email Sending** — Gmail sends out customized messages to leads.

---

## 📊 Data Output

| Field         | Description                     | Example                        |
|---------------|----------------------------------|--------------------------------|
| Company Name  | Business name from Yelp         | Best Local Restaurant          |
| Website       | Business URL                    | https://example-restaurant.com |
| Phone Number  | Contact number                  | (555) 123-4567                 |
| Email         | Email address                   | demo@example.com              |
| Address       | Physical address                | 123 Main St, City, State       |
| Rating        | Yelp/Trustpilot rating          | 4.5/5                          |
| Categories    | Business categories             | Restaurant, Italian, Fine Dining |

---

## 🚀 Setup Instructions

**⏱️ Estimated Time:** 10–15 minutes

### ✅ Prerequisites

- An `n8n` instance (cloud or self-hosted)
- Google account with Sheets access
- BrightData account (with Yelp & Trustpilot datasets)
- Google Gemini API access
- Anthropic API key (Claude AI)
- Gmail account

---

## 🔧 Step-by-Step Configuration

### 1. **Import Workflow into n8n**
- Copy the workflow JSON.
- In `n8n`: *Workflows → + Add workflow → Import from JSON*
- Paste and import.

### 2. **Configure Google Sheets**
- Create two Sheets:
  - `Yelp Data`: Name, Categories, Website, Address, Phone, URL, Rating
  - `Trustpilot Data`: Company Name, Email, Phone Number, Address, Rating, Company About
- Copy Sheet IDs from URLs.
- In `n8n`:
  - Go to *Credentials → Google Sheets OAuth2 API* → Add and connect.
  - Replace Sheet IDs in nodes.

### 3. **Configure BrightData**
- Set BrightData API credentials in n8n.
- Replace API token in workflow: `BRIGHT_DATA_API_KEY`
- Verify datasets:
  - Yelp: `gd_lgugwl0519h1p14rwk`
  - Trustpilot: `gd_lm5zmhwd2sni130p`

### 4. **Configure AI Models**
- **Gemini (Google AI):**
  - Set credentials and model: `models/gemini-1.5-flash`
- **Claude AI (Anthropic):**
  - Add API key and model: `claude-sonnet-4-20250514`

### 5. **Gmail Integration**
- Setup Gmail OAuth2 in `n8n`.
- Test email node: “Send Outreach Email”.

### 6. **Test & Activate**
- Start workflow with:
  - Country: United States
  - Location: Dallas
  - Category: Restaurants
- Verify:
  - Data appears in Sheets
  - Emails are generated/sent

---

## 📖 Usage Guide

### ✅ Starting Campaigns
1. Access form trigger URL.
2. Input:
   - Country
   - Location
   - Business Category
3. Submit to begin lead generation.

### 📊 Monitoring Results
- **Yelp Sheet**: Business info
- **Trustpilot Sheet**: Credibility data
- **Gmail Sent Items**: Sent emails

---

## ⚙️ Customization Options

### 🎨 Email Personalization
Edit the *“AI Generate Email Content”* node to modify:
- Tone
- Value proposition
- Call-to-actions
- Branding

### 🧰 Data Filters
- Set min rating/review count
- Filter by size or geo
- Focus by category

### 🚀 Scaling
- Increase batch sizes
- Add delay & error handling
- Use parallel execution

---

## 🚨 Troubleshooting

| Issue                      | Cause                            | Fix                                |
|---------------------------|-----------------------------------|-------------------------------------|
| BrightData Fails          | Invalid credentials               | Check token & dataset permissions  |
| No Data Returned          | Bad location/category             | Validate inputs                    |
| Gmail Send Errors         | Expired OAuth                     | Re-authenticate Gmail              |
| AI Model Failure          | API quota exceeded                | Check key and limits               |

---

## ⚡ Performance & Limits

| Metric              | Estimate                   |
|---------------------|----------------------------|
| Processing Speed    | 5–10 min/location          |
| Data Accuracy       | ~90%                       |
| Success Rate        | ~85%+                      |
| Daily Leads         | 100–500                    |
| API Calls/Lead      | ~10–20                     |
| Bandwidth/Lead      | ~5–10MB                    |

---

## 📈 Use Cases

1. **Digital Marketing Lead Gen** — Find businesses needing help with marketing.
2. **B2B Sales Prospecting** — Target fast-growing businesses for SaaS.
3. **Partnership Outreach** — Identify reputable businesses for alliances.

---

## 🤝 Support & Community

- [n8n Community](https://community.n8n.io)
- [n8n Docs](https://docs.n8n.io)
- BrightData Support: via dashboard

### 💡 Contributions
- Share improvements or templates
- Report bugs
- Customize for specific industries

---

## 🪪 License

This project is licensed under the [MIT License]
