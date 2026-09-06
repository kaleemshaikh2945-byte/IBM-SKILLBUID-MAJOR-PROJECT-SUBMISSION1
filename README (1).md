# AI-Powered Nutrition Agent

**Exploring the Power of Agentic AI with IBM Granite and IBM Bob**
IBM SkillsBuild for University Engagements — AICTE 2026 — Edunet Foundation

**Student:** Mohammad Kaleem Shaikh
**Domain:** Healthcare / Nutrition / Preventive Wellness
**Problem Statement:** AICTE Problem Statement No. 8 — Nutrition Agent

---

## Overview

The AI-Powered Nutrition Agent is a multi-agent Agentic AI system that provides
personalized nutrition guidance — diet planning, food-intake analysis, preventive
health advisories, and progress tracking. It is designed around **IBM Bob** for
agent orchestration, **IBM Granite** models for language understanding and
personalization, and **IBM watsonx.ai** for model deployment, embeddings, and
governance, with a **Retrieval-Augmented Generation (RAG)** pipeline grounding
every answer in trusted nutrition data.

## Problem Statement

Most existing nutrition tools give generic diet plans, don't adapt in real time,
and ignore a person's allergies, culture, or evolving health conditions.
Dieticians can't scale 1:1 consultations to everyone who needs them. This project
explores how Agentic AI can close that gap with an adaptive, always-available
virtual nutrition assistant — framed as informational support, **not** a medical
diagnosis tool.

## Architecture

```
User
  -> Nutrition Agent (front door)
    -> IBM Bob (agent orchestration)
      -> Nutrition Knowledge Agent   (RAG retrieval of food/nutrition facts)
      -> Diet Recommendation Agent   (personalized meal plans)
      -> Health Advisory Agent       (preventive, disease-specific guidance)
      -> Food Log & Feedback Agent   (meal logging + gap analysis)
        -> RAG / Vector Database (FAISS or Chroma)
          -> IBM Granite models (reasoning, summarization, personalization)
          -> IBM watsonx.ai (deployment, embeddings, governance)
            -> Nutrition Dashboard (plans, charts, advisories, progress)
```

See `docs/architecture.md` and `docs/agent_descriptions.md` for details.

## Agents

| Agent | Responsibility |
|---|---|
| Nutrition Knowledge Agent | Retrieves & summarizes nutrition facts (calories, macros, vitamins) via RAG |
| Diet Recommendation Agent | Builds personalized meal plans from age, goals, allergies, preferences |
| Health Advisory Agent | Preventive, disease-specific dietary suggestions (e.g. diabetes-friendly) |
| Food Log & Feedback Agent | Analyzes logged meals, flags nutritional gaps |

IBM Bob orchestrates hand-offs between these agents for every user request.

## Technology Stack

- IBM Bob — visual multi-agent orchestration
- IBM Granite models (e.g. `ibm-granite-3-2-8b`) — NLU, reasoning, personalization
- IBM watsonx.ai — model deployment, embeddings, AI governance
- IBM Cloud Lite — hosting infrastructure
- RAG pipeline + Vector Database (FAISS / Chroma)
- Python (agent logic, data processing)
- Streamlit / React (dashboard and chat interface)

## Repository Structure

```
nutrition-agent/
  agents/
    nutrition_knowledge_agent.py
    diet_recommendation_agent.py
    health_advisory_agent.py
    food_log_feedback_agent.py
    orchestrator_bob_config.json
  data/
    food_composition_dataset.csv
    sample_food_logs.json
  rag/
    embeddings_builder.py
    vector_store_faiss/
  dashboard/
    app.py            (Streamlit / React)
    components/
  prompts/
    diet_plan_prompt.txt
    food_analysis_prompt.txt
    heart_healthy_prompt.txt
  docs/
    architecture.md
    agent_descriptions.md
  README.md
  requirements.txt
```

## Demo Prompts Used for Project Output Evidence

1. *"Create a personalized 7-day nutrition plan for a 22-year-old vegetarian user
   whose goal is healthy weight management."*
2. *"Analyze today's food intake and identify calorie, protein, fiber and
   micronutrient deficiencies."*
3. *"Create a heart-healthy meal recommendation based on the user's dietary
   preferences and nutrition goals."*

## Setup Instructions (Prototype)

1. `pip install -r requirements.txt`
2. Build the vector store: `python rag/embeddings_builder.py`
3. Configure agents in IBM Bob using `agents/orchestrator_bob_config.json`
4. Run the dashboard: `streamlit run dashboard/app.py`

## Academic Honesty Notes

- Certificates included are genuine IBM SkillsBuild / Credly credentials issued
  to the student.
- Slides requiring a live IBM Bob capture (workspace screenshots, architecture
  blueprint view, token usage) are clearly marked "pending capture" rather than
  filled with fabricated evidence — replace them with real screenshots from
  your own IBM Bob session before final submission.
- UI/output screenshots in this repository are labeled **prototype / demo**
  and are not claimed to be live IBM Bob captures.
- No GitHub URL is invented; the repository link should be added here once
  created and tested.

## Future Scope

- Wearable & smartwatch integration for real-time activity data
- Voice assistant and multilingual support
- Image-based food recognition for instant meal logging
- Advanced predictive nutrient-deficiency analytics
- Integration with health devices (glucometers, BP monitors)
- Deeper personalization with regional/cultural food databases

## GitHub

**GitHub repository to be added after upload.** Suggested repository name:
`ai-powered-nutrition-agent`
