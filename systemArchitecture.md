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
1. **EEG Headset** captures neural signals.  
2. Signals processed locally by **Neuro Core chip**.  
3. Processed signals sent via **Bluetooth** to **mobile app**.  
4. Mobile app forwards data to **backend API** for storage and AI analysis.  
5. **AI engine** classifies emotional patterns and returns insights.  
6. Mobile app visualizes results; optionally transmits to paired user for instant emotional feedback.  
7. Database stores sessions, users, and emotional data for analytics.

---

## 🧠 Technical Feasibility
- EEG headsets and wearable sensors exist commercially (e.g., Muse, Emotiv).  
- Real-time data streaming via Bluetooth is achievable with current SDKs.  
- FastAPI backend handles API requests efficiently and scales with cloud infrastructure.  
- TensorFlow / Scikit-learn models can classify emotion patterns in milliseconds.  
- PostgreSQL ensures reliable storage and analytics capability.  
- Modular design allows future expansion: new wearables, offline mode, or additional sensory outputs.

---

## 🧭 System Diagram (Mermaid Visualization)
```mermaid
flowchart TD
    A[EEG Headset 🧠] -->|Brainwave Data| B[Neuro Core Chip ⚙️]
    B -->|Encrypted Bluetooth Stream| C[Mobile App 📱]
    C -->|API Request| D[Backend (FastAPI)]
    D -->|Sends Signals| E[AI/ML Engine 🤖]
    E -->|Emotion Vectors| F[(PostgreSQL DB 🗄️)]
    E -->|Insights| C
    C -->|Shared Output| G[Connected User 💫]
    subgraph Cloud ☁️
        D
        E
        F
    end

