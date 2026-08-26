# Audience
The "spell-check" for modern music production. An AI-powered platform that analyzes audio waveforms against multi-genre streaming retention data to predict human drop-off points, visually highlight attention valleys, and suggest structural arrangement fixes to optimize listener engagement before distribution.

# *Audience* - Software Blueprint & Implementation Timeline

## 1. Executive Concept Summary
*Audience* is an intelligent, data-driven "music grammar & spell-check" tool. It maps public streaming engagement metadata and video heatmaps directly against raw audio waveforms to predict human attention drop-off points. The software provides contextual, genre-specific arrangement corrections, allowing artists to maximize retention before publishing tracks natively to major streaming platforms.

---

## 2. System Architecture
```
                      [ PUBLIC WEB DATA SOURCES ]
               YouTube Heatmaps (JSON) / Spotify Skip Data
                                   │
                                   ▼ (Python Pipeline)
                      [ MULTI-GENRE DATA MATRIX ]
               Rap / R&B / Pop / Metal / Rock Sub-Models
                                   │
                                   ▼ (Feature Matching)
                   [ NEURAL NETWORK TRANSLATION CORE ]
                Audio Spectrogram Transformer Fine-Tuning
                                   │
                                   ▼ (Unified API)
             ┌─────────────────────┴─────────────────────┐
             ▼                                           ▼
   [ Hybrid Desktop/Web App ]                  [ DAW Plugin Licensing ]
    Electron Window GUI Framework               Pro Tools / Logic Pro SDK
```

---

## 3. GitHub Agile Development Roadmap (12-Week Timeline)

### Sprint 1-2: Data Engineering & Scraping Base (Weeks 1-2)
*   **Objective**: Harvest the primary training dataset.
*   **Tasks**:
    *   Build headless browser scrapers (`Playwright`/`Selenium`) to extract 100-point `intensityScoreNormalized` JSON arrays from target YouTube playlists.
    *   Download and structure the open-source *Spotify Sequential Skip Prediction Dataset*.
    *   Set up a PostgreSQL database to catalog tracks linked to their exact timestamp vectors.

### Sprint 4: Audio Feature Extraction Pipeline (Week 4)
*   **Objective**: Translate raw audio into mathematical inputs.
*   **Tasks**:
    *   Build automated scripts utilizing `Librosa` to calculate transients, spectral flatness, and RMS loudness on 3-second sliding windows.
    *   Align physical audio timelines directly with harvested viewer drop-off/peak timestamps.
    *   Train an unsupervised classifier to automatically sort uploaded tracks into appropriate genre matrices.

### Sprint 5-7: Neural Network Training & Optimization (Weeks 5-7)
*   **Objective**: Build the predictive AI engine.
*   **Tasks**:
    *   Import a pre-trained *Audio Spectrogram Transformer (AST)* or *MERT* model from Hugging Face.
    *   Fine-tune the model's final layers using the processed multi-genre data.
    *   Achieve an 80%+ cross-validation accuracy score on predicting human attention drops.

### Sprint 8-10: Frontend UI/UX & Waveform Rendering (Weeks 8-10)
*   **Objective**: Build the visual "Music Spell-Check" interface.
*   **Tasks**:
    *   Develop the user web/desktop environment using React and Electron.
    *   Implement an interactive audio waveform rendering engine (`Wavesurfer.js`).
    *   Overlay the real-time retention line plot and shade high-risk drop-off windows translucent crimson.
    *   Create the contextual "Suggestion Card" panel sidebar.

### Sprint 11-12: Publishing Bridges, Testing & Launch (Weeks 11-12)
*   **Objective**: Finalize distribution channels and launch beta.
*   **Tasks**:
    *   Wire up dummy metadata distribution pipelines (DDEX specifications) for future publishing expansions.
    *   Package the application binaries for local Windows testing.
    *   Deploy the initial 500-user closed-beta testing campaign.

---

## 4. GitHub Setup Instructions
1. Initialize the root repository: `git init audience-core`
2. Create separate branch folders: `/backend-scraper`, `/ml-engine`, `/desktop-gui`.
3. Utilize GitHub Projects to track individual Sprint issues and milestones sequentially.
