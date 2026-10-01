Model Personality Drift Tracker 🎯
<br>
<br>
A mobile-first cross-platform Flutter application to systematically probe, score, and visualize AI Model Personality & Behavioral Drift across model generations and version updates (e.g., Meta Llama 3 8B vs Llama 3.1 8B vs Llama 3.2 3B, Google Gemma 1 vs Gemma 2, Mistral 7B vs Nemo).

📌 The Problem: What is "Personality Drift"?
When model weights are updated with new RLHF (Reinforcement Learning from Human Feedback), DPO (Direct Preference Optimization), or system prompt calibrations, their conversational personality shifts—often unexpectedly:

Excessive Hedging: Models frequently inject defensive disclaimers ("As an AI language model...", "It is important to remember...") into harmless inquiries.
Verbosity Bloat: Models add conversational preamble and pleasantries instead of following conciseness constraints.
Sycophancy Shifts: Models may become overly agreeable and validating rather than offering objective, tough advice.
Stylistic Sanitization: Fine-tuning often suppresses humor, sarcasm, and expressive figurative voice.
Model Personality Drift Tracker gives developers and AI researchers a standardized evaluation arena and visual radar dashboard to quantify these shifts before rolling out new model versions.

🌟 Key Features
1. Multi-Model & Version Comparison Arena
Compare any Baseline (Model A) against a Candidate (Model B).
Pre-configured presets for popular open-source model series:
Meta Llama Series: llama-3-8b (Baseline) vs llama-3.1-8b (Mid) vs llama-3.2-3b (Edge)
Google Gemma Series: gemma-2-9b
Mistral Series: mistral-7b-instruct
Qwen Series: qwen-2.5-7b-instruct
Local / Custom Endpoints: Local Ollama (http://localhost:11434/api/chat or http://10.0.2.2:11434/api/chat), Groq, or Hugging Face.
2. Standardized Personality Benchmark Probes
Workplace Crisis Advice (Empathy Probe): Tests warmth, emotional validation, and sycophancy vs objective advice.
Ethical Rule-Breaking (Assertiveness & Hedging Probe): Probes whether the model takes a firm philosophical stance or retreats into non-committal disclaimers.
Quantum Superposition in 2 Sentences (Conciseness Probe): Tests instruction adherence vs conversational verbosity and introductory preamble bloat.
Pretentious Art Critic on Toasters (Whimsicality Probe): Evaluates vivid stylistic humor and figurative flair vs sanitization.
Refusal Tone & Boundary Probe (Safety Calibration): Evaluates refusal tone (preachy lecture vs neutral and constructive boundary).
Custom Probe Creator: Create and test your own prompts and hypotheses.
3. 6-Dimensional Personality & Linguistic Scoring Engine
Calculates normalized scores (0–100) across:

Warmth & Empathy
Assertiveness & Decisiveness
Formality & Professionalism
Verbosity & Elaboration
Hedging & Caution
Whimsicality & Expressiveness
Linguistic Stats: Word count, Flesch Reading Ease, disclaimer frequency, sentiment polarity, and inference latency.
4. Interactive Visualizations
Multi-Model Radar Chart (Spider Chart): Superimposes Model A (Cyan) and Model B (Purple) polygons with interactive touch inspection of dimension vertices.
Drift Delta Matrix: Visual badges highlighting percentage shifts (+34% Hedging ⚠️, -18% Directness, +42% Warmth).
Side-by-Side Response Inspector: Dual view with word count, latency, reading ease, and copy-to-clipboard functionality.
Historical Drift Timeline: Chronological log of past evaluations with drift severity indicators.
Export & Share: Generates clean Markdown / JSON audit reports for team review.
5. Instant Demo Replay Mode + Live API Mode
Pre-loaded with verified cross-version response data from Llama 3 vs Llama 3.1 vs Llama 3.2 across all 5 benchmark probe categories. Test immediately out of the box without requiring an API key!
Toggle to Live Mode in Settings to connect your OpenRouter, Groq, or local Ollama endpoints.
🚀 How to Run the App
Navigate to the project directory:

bash


cd C:\Users\Aarya\.gemini\antigravity\scratch\model_personality_drift_tracker
Option A: Double-Click Launcher (Windows)
Double-click either of these files inside the folder:

run_in_chrome.bat (Opens in Chrome with responsive mobile phone preview)
run_windows.bat (Runs as a native desktop application)
Option B: Terminal / Command Prompt
Run in Chrome:
bash


flutter run -d chrome
Run on Windows Desktop:
bash


flutter run -d windows
Run on an Android device or emulator:
bash


flutter run -d android
🧪 Automated Testing & Verification
Run the automated test suite (unit tests and UI smoke tests):

bash


flutter test
Run static analysis:

bash


flutter analyze
🛠️ Project Architecture
text

lib/
<br>
├── core/
<br>
│   └── theme/
<br>
│       └── app_theme.dart                 # Dark and light AI lab themes
<br>
├── data/
<br>
│   ├── models/
<br>
│   │   ├── model_info.dart                # Open-source model metadata and presets
<br>
│   │   ├── personality_metrics.dart       # 6D personality vectors & delta calculus
<br>
│   │   ├── probe_prompt.dart              # Benchmark probe definitions & categories
<br>
│   │   └── comparison_result.dart         # Cross-version comparison records
<br>
│   ├── services/
v
│   │   ├── open_source_ai_service.dart    # OpenRouter / Groq / Ollama / HF API client
<br>
│   │   ├── personality_analyzer.dart      # Deterministic NLP linguistic & personality scorer
<br>
│   │   └── mock_benchmark_data.dart       # Pre-seeded verified cross-version data
<br>
│   └── repositories/
<br>
│       └── drift_tracker_repository.dart  # History manager and report generator
<br>
├── ui/
<br>
│   ├── view_models/
<br>
│   │   └── drift_tracker_view_model.dart  # Reactive state management
<br>
│   ├── views/
<br>
│   │   ├── arena_view.dart                # Interactive comparison & prompt test arena
<br>
│   │   ├── radar_visualizer_view.dart     # Interactive radar chart & dimension matrix
<br>
│   │   ├── timeline_view.dart             # Chronological drift history
<br>
│   │   └── settings_view.dart             # Live API config, local Ollama, & temperature
<br>
│   └── widgets/
<br>
│       ├── radar_chart_widget.dart        # CustomPainter animated dual-model radar chart
<br>
│       ├── drift_delta_card.dart          # Dimension delta badge (+/- % changes)
<br>
│       ├── side_by_side_response.dart     # Dual split response viewer
<br>
│       ├── metric_bar_widget.dart         # Comparative linear score bars
<br>
│       └── mobile_container.dart          # Adaptive mobile frame container
<br>
└── main.dart                              # Application shell & entrypoint
<br>
<br>
The file is saved locally in your repository at: 
C:\Users\Aarya\.gemini\antigravity\scratch\model_personality_drift_tracker\README.md
