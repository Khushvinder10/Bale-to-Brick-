# 🌾 Bale to Brick
### Turning Crop Stubble into a Valuable Resource, Not Smoke.

**Bale to Brick** is an agricultural marketplace designed to transform crop stubble from an environmental challenge into an economic opportunity. The platform connects farmers, industrial buyers, and agricultural operators through a transparent, technology-driven marketplace.

Farmers can list their fields for stubble clearance, buyers such as brick kilns and biomass plants can discover suitable agricultural land, and operators can compete through a reverse auction system to provide affordable baling and transportation services.

By connecting all three stakeholders, Bale to Brick promotes sustainable agricultural practices, reduces crop residue burning, and creates new economic opportunities.

---

## 🚀 Key Features

### 👨‍🌾 1. Farmer Marketplace
- Register and manage farmer accounts.
- List agricultural land for stubble clearance.
- Specify crop type, land area, location, and clearance deadline.
- Submit land details using voice or text.
- Upload Jamabandi and Khatauni documents for AI-powered information extraction.
- Track clearance progress and confirm completed jobs.

### 🏭 2. Buyer Marketplace
- Discover available agricultural land by region and crop type.
- Filter listings according to price, location, and requirements.
- View land locations and nearby opportunities on an interactive map.
- Receive AI-powered fair-price recommendations.
- Select preferred operators through a competitive bidding process.
- Track ongoing and completed deals.

### 🚜 3. Operator Bidding System
- Discover available stubble-clearance jobs.
- Submit competitive bids based on price and completion time.
- Revise bids according to marketplace rules.
- Receive notifications when a buyer accepts a bid.
- Access exact field locations and transportation routes after deal confirmation.
- Upload photographic proof of completed work.

### 🤖 4. AI-Powered Intelligence
- Multilingual voice and text-based land listing.
- Automatic extraction of agricultural land details from documents.
- AI-generated environmental impact summaries.
- Smart baling recommendations.
- AI-powered price estimation.
- Photo-based verification of field clearance and bales.

### 🛰️ 5. Environmental Monitoring
- Satellite-based vegetation analysis using Google Earth Engine.
- Sentinel-2 NDVI and NDTI indicators for field assessment.
- NASA FIRMS fire detection integration.
- Zero-burn monitoring during the job lifecycle.
- Visual proof of completed stubble-clearance operations.

### 🔔 6. Real-Time Communication
- Live operator bidding updates.
- Instant notifications when bids are submitted.
- Deal confirmation notifications.
- SMS and OTP authentication support.
- Live marketplace updates using Server-Sent Events.

---

## 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Backend | Node.js, Express.js |
| Frontend | HTML, CSS, JavaScript |
| Database | SQLite |
| Authentication | JWT, Firebase Authentication |
| AI Integration | Gemini API, Gemma, Ollama |
| Maps & Navigation | Google Maps Platform, Routes API |
| Satellite Intelligence | Google Earth Engine, Sentinel-2 |
| Fire Detection | NASA FIRMS |
| Image Verification | Google Cloud Vision API |
| Price Prediction | Vertex AI |
| Real-Time Updates | Server-Sent Events |
| Cloud Deployment | Google Cloud Run, Firebase Hosting |
| Testing | Node.js Test Runner |
| Version Control | Git, GitHub |

---

## 🔗 Google Technologies Integration

Bale to Brick integrates multiple Google technologies to provide intelligent agricultural services.

| Google Technology | Implementation |
|---|---|
| Gemini API | Multilingual AI assistance, document extraction, impact summaries, and baling tips. |
| Gemma + Ollama | Local AI processing and offline capabilities. |
| Google Maps Platform | Satellite maps, location selection, village search, and navigation. |
| Routes API | Road distance, estimated travel time, and transportation cost calculations. |
| Google Earth Engine | Satellite-based field monitoring using Sentinel-2 data. |
| Firebase Authentication | Phone OTP and Google sign-in authentication. |
| Cloud Firestore | Optional real-time bid updates and notification synchronization. |
| Cloud Functions | Deal confirmation notifications. |
| Cloud Vision API | Verification of field-clearance and bale photographs. |
| Vertex AI | AI-based fair-price estimation. |
| Cloud Run | Containerized backend deployment. |
| Firebase Hosting | Frontend hosting with HTTPS support. |

**Explore the integrations:** Open `/#/tech` on the running application or select **Built with Google** in the footer.

---

## 🔄 How Bale to Brick Works

The platform follows a three-sided marketplace model involving farmers, buyers, and operators.

1. **Farmer Registration:** Farmers register and list their agricultural land with crop details, area, location, and clearance deadline.

2. **Buyer Discovery:** Buyers explore available land based on their preferred region, crop type, budget, and transportation requirements.

3. **Job Creation:** Buyers select suitable agricultural plots, establish a budget, and define a completion deadline.

4. **Operator Notifications:** Relevant operators receive notifications about available jobs.

5. **Reverse Auction:** Operators submit competitive bids based on service price and completion time.

6. **Bid Selection:** Buyers evaluate the bids and select their preferred operator.

7. **Deal Confirmation:** Once a bid is accepted, contact information, precise location, and transportation routes become accessible to the involved parties.

8. **Job Execution:** Operators complete the baling and transportation work and upload photographic evidence.

9. **Verification:** Farmers confirm job completion, and satellite-based zero-burn monitoring can be performed.

10. **Feedback:** Farmers and buyers rate the operator to improve marketplace transparency and accountability.

---

## 🔐 Privacy & Security

Privacy is an important part of the Bale to Brick architecture.

- Buyers and operators initially see approximate field locations rather than exact coordinates.
- Precise location information is unlocked only after a deal is confirmed.
- Uploaded land-record photographs are processed and discarded rather than permanently retained.
- Firestore stores limited operational counts and statuses.
- Authentication and server-side verification protect user accounts.
- API keys and application secrets should be configured through environment variables.

---

## ⚙️ Installation & Setup

### Prerequisites

Make sure you have the following installed:

- Node.js 22.13 or newer
- npm
- Git (optional, for cloning the repository)

**Note:** Bale to Brick uses Node.js built-in SQLite, so a separate database server is not required.

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd bale-to-brick
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create your environment file:

```bash
cp .env.example .env
```

Add the required configuration and optional Google API credentials to `.env`.

### 4. Start the Application

```bash
npm start
```

Open the application in your browser:

**http://localhost:3000**

### 5. Run Tests

```bash
npm test
```

The end-to-end test suite runs Google-related features against a mock Gemini implementation.

---

## 👤 Demo Accounts

On the first startup with an empty database, demonstration data is automatically loaded.

**Default demo password:** `demo1234`

| Role | Email |
|---|---|
| Farmer | farmer@demo.in |
| Farmer | farmer2@demo.in |
| Buyer | buyer@demo.in |
| Buyer | buyer2@demo.in |
| Operator | operator@demo.in |
| Operator | operator2@demo.in |
| Operator | operator3@demo.in |

To disable automatic demo-data seeding:

```env
DEMO_SEED=0
```

**OTP Demo Mode:** When SMS or email services are not configured, one-time verification codes are displayed on the screen.

---

## ☁️ Google Cloud Deployment

Bale to Brick supports deployment using Google Cloud Run and Firebase Hosting.

### Deploy Backend to Cloud Run

```bash
gcloud run deploy bale-to-brick \
  --source . \
  --region asia-south1 \
  --allow-unauthenticated \
  --max-instances 1 \
  --set-env-vars OTP_DEV_MODE=1
```

Configure your production environment variables and API secrets securely.

### Configure Firebase

Copy the Firebase configuration template:

```bash
cp .firebaserc.example .firebaserc
```

Add your Google Cloud/Firebase project ID to `.firebaserc`.

Deploy Firebase Hosting and Firestore rules:

```bash
firebase deploy --only hosting,firestore:rules
```

Optionally deploy Cloud Functions:

```bash
firebase deploy --only functions
```

**Deployment considerations:**

- SQLite data is stored inside the Cloud Run container and can reset when the instance restarts.
- The current configuration is suitable for demonstrations, not production-grade persistent storage.
- For production, migrate to Cloud SQL or another persistent database solution.
- Configure Firebase Authentication authorized domains.
- Restrict Google Maps API keys to authorized websites.
- Configure HTTPS and secure application secrets.

---

## 📁 Project Structure

```text
bale-to-brick/
│
├── src/
│   ├── google/
│   │   ├── ai/
│   │   ├── earth/
│   │   ├── firebase/
│   │   ├── routes/
│   │   ├── vertex/
│   │   └── vision/
│   │
│   ├── api.js
│   ├── api-google.js
│   ├── otp.js
│   ├── live.js
│   └── estimate.js
│
├── public/
│   └── Frontend application
│
├── functions/
│   └── Firebase Cloud Functions
│
├── test/
│   └── End-to-end tests
│
├── server.js
├── Dockerfile
├── firebase.json
├── firestore.rules
├── package.json
├── .env.example
└── README.md
```

---

## 🌍 Environmental & Social Impact

Bale to Brick aims to create value for multiple stakeholders while addressing agricultural residue management challenges.

- **For Farmers:** Additional income opportunities and convenient access to stubble-clearance services.
- **For Buyers:** Reliable access to agricultural residue as an alternative biomass resource.
- **For Operators:** Business opportunities through competitive service bidding.
- **For the Environment:** Reduced dependence on crop residue burning and better utilization of agricultural waste.

The platform aims to contribute towards a more sustainable agricultural ecosystem through technology and collaboration.

---

## 🚧 Future Enhancements

The following features are not yet included in the current implementation:

- Integrated online payments and escrow services.
- Dedicated administrative dashboard.
- Production-grade persistent database infrastructure.
- Advanced environmental impact analytics.
- Expanded regional language support.
- More comprehensive satellite-based verification.
- Enhanced operator performance and reputation analytics.

---

## ⚠️ Production Readiness

Before making the application publicly available:

- Replace the development JWT secret with a strong production secret.
- Disable development OTP mode.
- Configure production SMS and email services.
- Restrict API keys and configure appropriate permissions.
- Enable HTTPS.
- Implement persistent database storage and regular backups.
- Review authentication, authorization, and Firestore security rules.

---

## 💡 Our Vision

**Waste should not become smoke when it can become a resource.**

Bale to Brick envisions a future where agricultural residue creates economic opportunities instead of contributing to air pollution.

By bringing farmers, buyers, and operators onto one intelligent marketplace, we aim to build a more connected, efficient, and sustainable agricultural ecosystem.

---

**Built with ❤️ for sustainable agriculture and a cleaner future.**.
