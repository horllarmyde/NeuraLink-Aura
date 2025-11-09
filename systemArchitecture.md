# ⚙️ System Architecture – NeuroLink Aura

## 🏗️ Technology Stack
| Layer | Technology / Tool |
|-------|-----------------|
| Frontend | React Native (cross-platform iOS/Android app) |
| Backend | Python (FastAPI REST API) |
| Database | PostgreSQL (AWS RDS) |
| AI/ML | TensorFlow & Scikit-learn for emotion classification |
| Device | EEG headset / smart headband with Neuro Core chip |
| Connectivity | Bluetooth 5.0 + HTTPS API |

---

## 🔗 Component Communication
1. EEG headset detects neural signals.  
2. Neuro Core chip processes signals locally and encrypts them.  
3. Signals sent via Bluetooth to the mobile app.  
4. Mobile app forwards data to backend API for AI processing.  
5. AI engine classifies emotional patterns and returns insights.  
6. Mobile app visualizes results; optionally transmits to paired user.  
7. Database stores session, user, and emotion data for analytics.

---

## 🧠 Technical Feasibility
- EEG headsets and wearable sensors exist commercially (e.g., Muse, Emotiv).  
- Real-time Bluetooth streaming is achievable with current SDKs.  
- FastAPI backend handles API requests efficiently and scales with cloud infrastructure.  
- TensorFlow / Scikit-learn models can classify emotion patterns in milliseconds.  
- PostgreSQL ensures reliable storage and analytics capability.  
- Modular design allows future expansion: new wearables, offline mode, or additional sensory outputs.

---

## 🧭 System Diagram (Mermaid Visualization)

```mermaid
graph TD
  A[User Interface] --> B[Frontend Application]
  B --> C[Backend API]
  C --> D[Authentication Service]
  C --> E[Database]
  C --> F[External APIs]
  E --> G[(Data Storage)]
  F --> H[Third-party Services]
  D --> I[Identity Provider]
