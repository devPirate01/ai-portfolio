---
layout: splash
author_profile: false
classes: wide
title: "Mohammed Mahdi Jahangiri"
header:
  overlay_color: "#0b1f33"
  overlay_filter: "0.55"
  overlay_image: /assets/images/hero.jpg
  actions:
    - label: "View projects"
      url: "#projects"
    - label: "Contact"
      url: "#contact"
excerpt: "AI Engineer / Machine Learning Engineer. Specialising in Python, PyTorch, Hugging Face, NLP pipelines, LLM fine-tuning, RAG, and AI Safety."
---

## Featured Work {#projects}

Projects demonstrating AI engineering, machine learning pipelines, LLM integration, and AI safety research.

<div class="project-card">
  <div class="project-card__media">
    <div class="project-media-viewer" id="viewer-skyrim">
      <div class="viewer-nav">
        <button class="active" onclick="showMedia('viewer-skyrim', 0)">Media</button>
        <button onclick="showMedia('viewer-skyrim', 1)">Architecture</button>
        <button onclick="showMedia('viewer-skyrim', 2)">Code</button>
      </div>
      <div class="viewer-slides">
        <div class="slide active">
          <img src="{{ '/assets/images/skyrim-hero.jpg' | relative_url }}" alt="Skyrim LLM companion prototype" loading="lazy" />
        </div>
        <div class="slide">
<pre class="diagram">
[Creation Kit Engine: CompanionLLMV01.esp]
        ↓
[Papyrus Hook: In-Game Event Trigger]
        ↓ (Writes request.json via JContainers)
[Python LLM Bridge & Orchestrator]
    ├── [data_director.py]         → Session Memory & RAG Retrieval
    ├── [llm_payload_builder.py]   → Profile & State Prompt Injection
    ├── [KoboldCpp / OpenWebUI]    → Local LLM Inference Execution
    └── [llm_reply_processor.py]   → JSON Sanitisation & Policy Check
        ↓ (Writes response.json via JContainers)
[Game Quest Engine: MMJ_Script]
</pre>
        </div>
        <div class="slide">
{% highlight python %}
# Sent with prompt payload to define output contract for local LLM
def build_output_contract() -> dict:
    return {
        "schema_version": OUTPUT_SCHEMA_VERSION,
        "dialogue": "Short player-facing NPC dialogue",
        "player_intent": "One allowed intent",
        "topic": "One allowed topic",
        "policy_id": "One policy available to this NPC",
        "response_type": "One allowed response type",
        "clue_claims": ["Zero or more clue IDs"],
        "action_request": None,
    }
{% endhighlight %}
        </div>
      </div>
    </div>
  </div>
  <div class="project-card__content">
    <h3>MSc Thesis — Safe AI Companion Systems (Skyrim LLM Bridge)</h3>
    <p class="project-card__meta"><strong>Python, RAG, Local LLMs, JSON APIs, Prompt Engineering, C++</strong></p>
    <p>MSc thesis prototype establishing a safe, local LLM pipeline with retrieval-augmented generation (RAG).</p>
    <ul>
      <li>Built a custom local AI companion pipeline using <strong>Python</strong>, <strong>RAG-style context retrieval</strong>, and structured <strong>JSON request/response</strong> interfaces.</li>
      <li>Engineered a local LLM orchestration bridge with bounded context windows, safety constraints, and prompt-engineering guardrails.</li>
      <li>Evaluated the AI agent against branching-dialogue baselines, measuring interaction quality, latency, safety, and reliability metrics.</li>
    </ul>
  </div>
</div>

<div class="project-card">
  <div class="project-card__media">
    <div class="project-media-viewer" id="viewer-aiscu">
      <div class="viewer-nav">
        <button class="active" onclick="showMedia('viewer-aiscu', 0)">Media</button>
        <button onclick="showMedia('viewer-aiscu', 1)">Overview</button>
      </div>
      <div class="viewer-slides">
        <div class="slide active">
          <img src="{{ '/assets/images/AISafty-hero.jpg' | relative_url }}" alt="AI Safety Cardiff University" loading="lazy" />
        </div>
        <div class="slide">
<pre class="diagram">
[AI Safety Cardiff University (AISCU)]
        ↓ (Spring 2026 Fundamentals Fellowship)
[Research & Evaluation Domains]
    ├── Catastrophic AI Risks & Governance
    ├── Reward Hacking & Specification Gaming
    ├── Deception, Scheming & Model Evals
    └── Cyber Risks & AI / Biosecurity
        ↓
[Focus: AI Safety, Biosecurity & Human Autonomy]
</pre>
        </div>
      </div>
    </div>
  </div>
  <div class="project-card__content">
    <h3>AI Safety Cardiff University (AISCU) — Founding Fellow</h3>
    <p class="project-card__meta"><strong>AI Safety, Model Evaluation, AI Governance, Biosecurity, Risk Alignment</strong></p>
    <p>Founding member and fellow of the Spring 2026 Fundamentals Fellowship at AI Safety Cardiff University.</p>
    <ul>
      <li>Completed intensive fellowship analyzing <strong>catastrophic AI risks</strong>, <strong>reward hacking/specification gaming</strong>, <strong>deception & scheming</strong>, and <strong>model evaluations</strong>.</li>
      <li>Studied <strong>AI governance</strong> frameworks, <strong>cyber risks</strong>, and safety controls at the biosecurity interface of frontier AI models.</li>
      <li>Developed focused research interest in the overlap between AI systems, <strong>biosecurity</strong>, behavioral data, privacy, and human autonomy.</li>
    </ul>
  </div>
</div>

<div class="project-card">
  <div class="project-card__media">
    <div class="project-media-viewer" id="viewer-apoceus">
      <div class="viewer-nav">
        <button class="active" onclick="showMedia('viewer-apoceus', 0)">Media</button>
        <button onclick="showMedia('viewer-apoceus', 1)">Code</button>
      </div>
      <div class="viewer-slides">
        <div class="slide active">
          <img src="{{ '/assets/images/apoceus-hero.jpg' | relative_url }}" alt="Apoceus Winter Wars gameplay and team workflow" loading="lazy" />
        </div>
        <div class="slide">
{% highlight csharp %}
// Radial search algorithm optimizing unit placement and avoiding inefficient .Sum() allocations
int maxNumberOfSurroundingCircles = 50;
int[] expectedPositionCounts = new int[maxNumberOfSurroundingCircles];
float[] angleIncValues = new float[maxNumberOfSurroundingCircles];
float[] currentAngles = new float[maxNumberOfSurroundingCircles];
float[] offsets = new float[maxNumberOfSurroundingCircles];

int currentTotalPositions = 0;
for (int i = 0; currentTotalPositions < amount && i < maxNumberOfSurroundingCircles; i++) 
{
    offsets[i] = offset * (i + 1);
    expectedPositionCounts[i] = Mathf.FloorToInt(2.0f * Mathf.PI * offsets[i] / ((refUnit.Radius + spacing) * 2.0f));
    if (expectedPositionCounts[i] == 0) expectedPositionCounts[i] = 1;
        
    angleIncValues[i] = 360f / expectedPositionCounts[i]; 
    currentAngles[i] = 0.0f;
    currentTotalPositions += expectedPositionCounts[i];
}
{% endhighlight %}
        </div>
      </div>
    </div>
  </div>
  <div class="project-card__content">
    <h3>Engineering Team Lead — Landell Games (Apoceus)</h3>
    <p class="project-card__meta"><strong>Agile/Scrum, Technical Leadership, Performance Profiling, Git/Plastic SCM, Steam</strong></p>
    <p>Production engineering and team coordination on a live-service software project shipping to Steam.</p>
    <ul>
      <li>Coordinated a <strong>3–6 person engineering team</strong>, translating production priorities into sprint tasks and raising sprint success from <strong>40% to 90%</strong>.</li>
      <li>Profiled and optimized performance bottlenecks, improving frame time by <strong>10–30 FPS</strong> on target hardware.</li>
      <li>Conducted rigorous <strong>code reviews</strong> and enforced clean branch hygiene across a remote engineering team.</li>
      <li>Owned weekly build pipelines and mediated cross-functional technical concerns between <strong>5 department leads</strong>.</li>
    </ul>
    <div class="project-links">
      <a href="https://store.steampowered.com/app/1841690/Apoceus_Winter_Wars/" class="btn btn--primary" target="_blank" rel="noopener noreferrer">View on Steam →</a>
    </div>
  </div>
</div>

<div class="project-card">
  <div class="project-card__media">
    <div class="project-media-viewer" id="viewer-ai">
      <div class="viewer-nav">
        <button class="active" onclick="showMedia('viewer-ai', 0)">Architecture</button>
      </div>
      <div class="viewer-slides">
        <div class="slide active">
<pre class="diagram">
[Player Microphone Input]
        ↓
[Unreal C++ Mic Capture]
        ↓ (HTTP REST API)
[Python FastAPI Microservice]
    ├── [Whisper] → Real-time Speech-to-Text
    ├── [Wit.ai] → Intent Classification
    └── [Hugging Face] → Voice Emotion Model
        ↓ (JSON Response)
[Unreal Behavior Tree] → Real-time Action Logic
</pre>
        </div>
      </div>
    </div>
  </div>
  <div class="project-card__content">
    <h3>AI-Driven NPC Interaction Prototype</h3>
    <p class="project-card__meta"><strong>Python, FastAPI, PyTorch, Hugging Face, C++, Unreal Engine 5, Whisper, Wit.ai</strong></p>
    <p>A real-time, voice-driven AI pipeline bridging microphone audio to autonomous C++ behavior logic.</p>
    <ul>
      <li>Built a local <strong>Python FastAPI</strong> server bridging real-time microphone input to a <strong>C++</strong> application via a custom <strong>REST API</strong>.</li>
      <li>Integrated <strong>Whisper</strong> (speech-to-text), <strong>Wit.ai</strong> (intent detection), and local <strong>Hugging Face</strong> transformers for real-time voice and emotion detection.</li>
      <li>Trained the voice-emotion model and configured custom <strong>Wit.ai</strong> intents using voice dataset recordings.</li>
      <li>Wired microphone audio capture in <strong>C++</strong>, returning intent and emotion signals to drive real-time <strong>behavior-tree</strong> decision logic.</li>
    </ul>
  </div>
</div>

<div class="project-card">
  <div class="project-card__media">
    <div class="project-media-viewer" id="viewer-ichora">
      <div class="viewer-nav">
        <button class="active" onclick="showMedia('viewer-ichora', 0)">Presentation</button>
        <button onclick="showMedia('viewer-ichora', 1)">In-Game</button>
      </div>
      <div class="viewer-slides">
        <div class="slide active">
          <img src="{{ '/assets/images/ichora-photo.jpg' | relative_url }}" alt="Research poster and presentation for ICHORA conference" loading="lazy" />
        </div>
        <div class="slide">
          <img src="{{ '/assets/images/ichora-ingame.jpg' | relative_url }}" alt="In-game NPC dialogue interaction" loading="lazy" />
        </div>
      </div>
    </div>
  </div>
  <div class="project-card__content">
    <h3>Publication — ICHORA 2024</h3>
    <p class="project-card__meta"><strong>LLMs, NLP, Pursuit Learning Automata, Machine Learning Research</strong></p>
    <p><strong>Balancing Game Satisfaction and Resource Efficiency: LLM and Pursuit Learning Automata for NPC Dialogues</strong></p>
    <ul>
      <li>Published and presented peer-reviewed research proposing a resource-efficient local <strong>LLM pipeline</strong> for dynamic dialogue.</li>
      <li>Applied <strong>pursuit learning automata</strong> to balance player interaction quality against local computational overhead.</li>
      <li>Demonstrated real-time feasibility of hybrid machine learning models in resource-constrained environments.</li>
    </ul>
    <div class="project-links">
      <a href="https://scholar.google.com/scholar?q=Balancing+Game+Satisfaction+and+Resource+Efficiency+LLM+Pursuit+Learning+Automata+NPC+Dialogues" class="btn btn--primary" target="_blank" rel="noopener noreferrer">View on Google Scholar →</a>
    </div>
  </div>
</div>

## About {#about}

**AI Engineer / Machine Learning Engineer**

AI Engineer with published research on LLM-driven dialogue systems (**ICHORA 2024**) and hands-on experience building **NLP pipelines**, fine-tuning models, and deploying AI via **REST APIs**. Founding fellow at **AI Safety Cardiff University**.

<div class="project-links">
  <a href="{{ '/about/' | relative_url }}" class="btn btn--inverse">Read Full Profile</a>
</div>

## CV {#cv}

<div class="project-links">
  <a href="{{ '/cv/' | relative_url }}" class="btn btn--primary">View CV Document</a>
  <a href="{{ '/assets/Mahdi_CV_Overleaf_AI.pdf' | relative_url }}" class="btn btn--inverse" download>Download PDF</a>
</div>

## Contact {#contact}

Available for AI Engineering, Machine Learning, and AI Safety roles.

- **Email:** <a href="mailto:mapjiv@live.com">mapjiv@live.com</a>
- **LinkedIn:** <a href="https://www.linkedin.com/in/m-mahdi-jahangiri/" target="_blank" rel="noopener noreferrer">linkedin.com/in/m-mahdi-jahangiri</a>
- **GitHub:** <a href="https://github.com/devPirate01" target="_blank" rel="noopener noreferrer">github.com/devPirate01</a>

<!-- Theme-Compliant Media & Code Lightbox Modal -->
<div id="media-modal" class="media-modal-backdrop" onclick="closeMediaModal(event)">
  <div class="media-modal-container" onclick="event.stopPropagation()">
    <div class="media-modal-header">
      <span class="media-modal-title"><span>●</span> Expanded View</span>
      <button class="media-modal-close" onclick="closeMediaModal(event)" title="Close (Esc)">✕</button>
    </div>
    <div class="media-modal-body" id="media-modal-body"></div>
  </div>
</div>

<script>
// Tab switcher logic
function showMedia(viewerId, index) {
  const viewer = document.getElementById(viewerId);
  if (!viewer) return;
  const buttons = viewer.querySelectorAll('.viewer-nav button');
  const slides = viewer.querySelectorAll('.slide');
  
  buttons.forEach((btn, i) => {
    if (i === index) btn.classList.add('active');
    else btn.classList.remove('active');
  });
  
  slides.forEach((slide, i) => {
    if (i === index) slide.classList.add('active');
    else slide.classList.remove('active');
  });
}

// Click-to-expand Lightbox Modal
function openMediaModal(contentElement) {
  let modal = document.getElementById('media-modal');
  const modalBody = document.getElementById('media-modal-body');
  if (!modal || !modalBody) return;
  
  // Attach directly to document.body to bypass layout overflow clipping
  if (modal.parentNode !== document.body) {
    document.body.appendChild(modal);
  }
  
  modalBody.innerHTML = contentElement.innerHTML;
  
  // Enforce explicit inline styles alongside CSS class
  modal.style.display = 'flex';
  modal.style.opacity = '1';
  modal.style.visibility = 'visible';
  modal.style.pointerEvents = 'auto';
  modal.classList.add('is-active');
  
  document.body.style.overflow = 'hidden';
}

function closeMediaModal(event) {
  if (event && event.target !== event.currentTarget && !event.target.classList.contains('media-modal-close')) return;
  const modal = document.getElementById('media-modal');
  if (!modal) return;
  
  modal.style.opacity = '0';
  modal.style.visibility = 'hidden';
  modal.style.pointerEvents = 'none';
  modal.classList.remove('is-active');
  
  setTimeout(() => {
    if (!modal.classList.contains('is-active')) {
      modal.style.display = 'none';
    }
  }, 250);
  
  document.body.style.overflow = '';
}

document.addEventListener('DOMContentLoaded', () => {
  document.querySelectorAll('.viewer-slides .slide').forEach(slide => {
    slide.addEventListener('click', (e) => {
      // Ignore click if user is selecting text
      if (window.getSelection && window.getSelection().toString().length > 0) return;
      openMediaModal(slide);
    });
  });
});

document.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') closeMediaModal();
});
</script>