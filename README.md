# Automated Media Publishing Pipeline

## Overview
Automated system that ingests tech news, filters relevance using LLMs, generates narrated short-form videos, and publishes them to YouTube with minimal human intervention.

Designed to run unattended with state tracking, failure handling, and operational notifications.

---

## Tech Stack
- **n8n** – workflow orchestration  
- **Docker / Docker Compose** – service management  
- **FFmpeg** – video assembly  
- **APIs** – RSS, LLM (Gemini), TTS (ElevenLabs), Stock Video (Pexels), YouTube Data API  
- **Slack** – operational notifications  

---

## High-Level Flow
1. Scheduled RSS ingestion  
2. Deduplication against previously processed items  
3. LLM relevance check (skip non-tech content)  
4. Script generation (hook / value / action)  
5. Audio narration generation  
6. Stock video discovery and download  
7. Video assembly via FFmpeg  
8. Resumable upload to YouTube  
9. Status tracking and Slack notification  

---

## Reliability & Operations
- Idempotent processing (no duplicate uploads)  
- Explicit skip paths for non-relevant content  
- Retry and continue-on-error logic  
- State persisted outside workflow execution  
- Rate limiting to avoid API throttling  

---

## Deployment
- Runs on a Linux host using Docker Compose  
- Secrets managed via n8n credential isolation  
- Designed for long-running, unattended execution  

---

## What This Demonstrates
- End-to-end system ownership  
- Automation of multi-stage media pipelines  
- Integration of multiple external services  
- Operational thinking (failure handling, retries, state)  

---

## Future Improvements
- Queue-based workers  
- Metrics and alerting  
- Object storage for media assets  
- Parallel processing stages  

> The included workflow file is a redacted export.
> All credentials, secrets, identifiers, and production endpoints have been removed.
> Structure, control flow, and operational logic are preserved for review.
