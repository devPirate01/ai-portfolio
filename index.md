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
excerpt: "AI Engineer / Machine Learning Engineer. Specialising in Python, PyTorch, Hugging Face, NLP pipelines, LLM fine-tuning, and AI Safety."
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
[Creation Kit Mod: CompanionLLMV01.esp]
        ↓
[Papyrus In-Game Hook: MMJ_TavernWitnessChatLauncher]
        ↓ (Writes request.json via JContainers / PapyrusUtil)
        ↓
[Python Orchestrator: bridge.py]
    ├── [data_director.py]         → IO, Session Memory, & Logging 
    ├── [llm_payload_builder.py]   → Profile & Quest State Prompt Injection
    ├── [Local Inference Engine]   → Gemma-4-E2B (Fine-Tuned SLM Execution)
    └── [llm_reply_processor.py]   → JSON Sanitisation & Quest Policy Validation
        ↓
        ↓ (Writes response.json via JContainers / PapyrusUtil)
[Skyrim Quest Engine: MMJ_PoisonedMeadQuestScript]
</pre>
        </div>
        <div class="slide">
{% highlight python %}
#This is sent with the main prompt to give a template for the llm's reply
def build_output_contract() -> Dict[str, Any]:
    """
    Defines the strict JSON schema contract for the LLM output.
    The response must strictly adhere to this structure to pass 
    the Papyrus state-machine validation layer.
    """
    return {
        "schema_version": "1.0",
        "dialogue": "Short, 1-3 sentence player-facing NPC dialogue.",
        "player_intent": "Selected from allowed intents (e.g., 'ask_for_information').",
        "topic": "Selected from allowed topics (e.g., 'suspect', 'weapon').",
        "policy_id": "One specific state-machine policy available to this NPC.",
        "response_type": "Must strictly align with the chosen policy_id.",
        "clue_revealed": ["Zero or more validated clue IDs (e.g., 'C1')"],
        "action_request": None,
    }
{% endhighlight %}
        </div>
      </div>
    </div>
  </div>
  <div class="project-card__content">
    <h3>MSc Thesis — Safe AI Companion Systems (Skyrim LLM Bridge)</h3>
    <p class="project-card__meta"><strong>Python, Fine-Tunning, Local LLMs, JSON APIs, Prompt Engineering, C++</strong></p>
    <p>MSc thesis prototype establishing a safe, Fine-tunned local LLM pipeline.</p>
    <ul>
      <li>Engineered a custom Skyrim AI mod using the <strong>Creation Kit</strong>, bridging deterministic <strong>Papyrus</strong> scripts with generative AI via a custom <strong>Python LLM orchestrator</strong>.</li>
      <li>Designed a secure inference pipeline with strict bounded context, state-machine validation, and automated fallback logic to prevent hallucinated quest flags.</li>
      <li>Executed rigorous automated benchmarking to evaluate the system against branching-dialogue baselines, measuring state routing accuracy, edge-inference latency, and strict JSON compliance.</li>
      <li><strong>Fine-tuned a Gemma 4 (E2B)</strong> model via QLoRA (4-bit quantization) to perfectly couple immersive, lore-accurate Skyrim dialogue with precise, game-ready JSON action states (on AMD RX 6900).</li>
    </ul>
    <div class="project-links">
      <a href="https://github.com/devPirate01/SkyrimLLMBridge" class="btn btn--primary" target="_blank" rel="noopener noreferrer">View on GitHub →</a>
      <a href="#" class="btn btn--inverse" onclick="return false;">Nexus Mod (in progress)</a>
    </div>
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