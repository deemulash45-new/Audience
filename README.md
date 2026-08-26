# Audience — Software Blueprint & Operational Master Plan

## 1. Executive Concept Summary
Audience is an intelligent, data-driven "music grammar & spell-check" tool. It maps public streaming engagement metadata and video heatmaps directly against raw audio waveforms to predict human attention drop-off points. The software provides contextual, genre-specific arrangement corrections, allowing artists to maximize retention before publishing tracks natively to major streaming platforms.

## 2. System Architecture
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

## 3. GitHub Agile Development Roadmap (12-Week Timeline)

### Sprint 1-2: Data Engineering & Scraping Base (Weeks 1-2)
- Build headless browser scrapers (Playwright/Selenium) to extract 100-point intensityScoreNormalized JSON arrays from target YouTube playlists.
- Download and structure the Spotify Sequential Skip Prediction Dataset.
- Set up a PostgreSQL database to catalog tracks linked to their exact timestamp vectors.

### Sprint 4: Audio Feature Extraction Pipeline (Week 4)
- Use Librosa to calculate transients, spectral flatness, and RMS loudness on 3-second sliding windows.
- Align physical audio timelines with viewer drop-off/peak timestamps.
- Train an unsupervised classifier to sort uploaded tracks into genre matrices.

### Sprint 5-7: Neural Network Training & Optimization (Weeks 5-7)
- Import a pre-trained AST or MERT model from Hugging Face.
- Fine-tune the model using the multi-genre dataset.
- Achieve 80%+ cross-validation accuracy on predicting attention drops.

### Sprint 8-10: Frontend UI/UX & Waveform Rendering (Weeks 8-10)
- Build the React/Electron hybrid app.
- Implement waveform rendering using Wavesurfer.js.
- Overlay retention plots and highlight drop-off zones.
- Add contextual suggestion cards.

### Sprint 11-12: Publishing Bridges, Testing & Launch (Weeks 11-12)
- Implement dummy DDEX metadata pipelines.
- Package Windows binaries.
- Launch a 500-user closed beta.

## 4. GitHub Setup Instructions
1. `git init audience-core`
2. Create folders: `/backend-scraper`, `/ml-engine`, `/desktop-gui`
3. Use GitHub Projects for sprint tracking.
