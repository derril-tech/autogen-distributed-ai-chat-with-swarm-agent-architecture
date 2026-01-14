# 🧠 SwarmChat
**Distributed AI Chat with Multi-Agent Architecture**

> **Ask a question once. Watch four specialized AI agents collaborate in real time—then receive a polished, consolidated answer that synthesizes their collective intelligence.** ⚡

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Next.js](https://img.shields.io/badge/Next.js-16-black.svg)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.2-61DAFB.svg)](https://react.dev/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Async-green.svg)](https://fastapi.tiangolo.com/)
[![Railway](https://img.shields.io/badge/Deploy-Railway-blueviolet.svg)](https://railway.app/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-black.svg)](https://vercel.com/)

---

## ✨ What It Does

SwarmChat demonstrates a **transparent multi-agent AI system** where four specialized agents work together to answer complex questions:

1. **Researcher** — Analyzes the question, identifies key facts, and outlines research avenues
2. **Critic** — Reviews findings, identifies gaps, and highlights potential risks
3. **Explainer** — Synthesizes information into clear, structured explanations
4. **Summarizer** — Consolidates all perspectives into a polished final answer

Every step of the collaboration is **streamed in real time**, giving you complete visibility into how the agents think, debate, and refine their responses.

---

## 🎯 Core Features

### 🤖 **Multi-Agent Orchestration**
- **Four Specialized Agents** — Each with distinct roles and optimized prompts
- **Round-Based Collaboration** — Agents build on each other's work across multiple rounds
- **Intelligent Context Sharing** — Agents see previous outputs and thread history
- **Optimized Prompts** — Fine-tuned system prompts for maximum quality and coherence

### 📡 **Real-Time Transparency**
- **Live Streaming** — Watch agent responses appear in real time via Server-Sent Events (SSE)
- **Per-Agent Panels** — Dedicated views for each agent's contributions
- **Run Timeline** — Visual progression from queued → running → completed
- **Message History** — Complete transcript of all agent interactions

### 🎨 **Advanced Conversation UX**
- **State-Driven UI** — Smooth transitions without page reloads
- **Dark/Light Mode** — Beautiful theme system with system preference support
- **Mobile-Optimized** — Responsive design with 44px+ touch targets, bottom navigation, and hamburger menu
- **Hero Video Backgrounds** — Immersive landing experience with theme-aware videos (disabled on mobile for performance)
- **Interactive Analytics** — Dashboard with thread search, statistics, and performance metrics
- **Toast Notifications** — Beautiful Sonner toasts with perfect centering, thick borders, and smart dismissal logic
- **Markdown Rendering** — Rich text formatting in all chat messages with theme-aware prose styling
- **Citation Extraction** — Automatic URL extraction and display from agent responses

### 📊 **Rich Feature Set**
| Feature | Description |
|---------|-------------|
| 🎯 **Real-Time Streaming** | SSE-based event streaming for live agent updates with toast notifications |
| 📝 **Thread Management** | Create, list, search, paginate (6 per page), and delete conversation threads |
| 📈 **Analytics Dashboard** | Comprehensive statistics and agent performance metrics with error handling |
| 🔍 **Thread Search** | Full-text search across thread titles and content with URL state management |
| 📤 **Export Functionality** | Download threads as Markdown or JSON from multiple locations |
| 📊 **Run Performance Metrics** | Real-time duration, message counts, and agent activity breakdown with polling |
| 🔄 **Thread Comparison** | Side-by-side comparison with dropdown selection, markdown rendering, and export |
| 📱 **Mobile Navigation** | Bottom nav and hamburger menu with improved contrast and touch targets |
| 🎨 **Theme System** | Complete light/dark mode with smooth transitions and semantic color tokens |
| 💾 **Full Persistence** | All conversations saved to Supabase PostgreSQL with automatic title generation |
| 🔗 **Citation Extraction** | Automatic URL extraction and display from agent responses |
| 🎨 **Markdown Rendering** | Rich text formatting in all chat messages with code blocks and links |
| 🔔 **Toast Notifications** | Beautiful, centered toasts with thick borders and smart dismissal |
| 🗑️ **Delete Functionality** | Permanent thread deletion with beautiful confirmation dialogs |

---

## 🏗️ Tech Stack

### **Frontend** ⚛️
| Technology | Purpose |
|------------|---------|
| **Next.js 16.0.10** | React framework with App Router, Server Components, and Suspense |
| **React 19.2** | Latest React with concurrent features, transitions, and useTransition |
| **TypeScript** | Type-safe development with strict mode |
| **Tailwind CSS** | Utility-first styling with custom design system and typography plugin |
| **shadcn/ui** | Beautiful, accessible component library (Button, Card, Dialog, Select, Tabs, Accordion, Sheet) |
| **Sonner** | Toast notification system with perfect centering and theme support |
| **react-markdown** | Markdown rendering for chat messages with syntax highlighting |
| **Server-Sent Events** | Real-time event streaming from backend |
| **date-fns** | Date formatting and relative time calculations |

### **Backend** 🐍
| Technology | Purpose |
|------------|---------|
| **FastAPI** | High-performance async Python API framework |
| **OpenAI GPT-4o-mini** | Advanced language model for agent responses (cost-optimized) |
| **Pydantic v2** | Data validation and settings management |
| **Async/Await** | Non-blocking I/O for optimal performance |

### **Data & Infrastructure** 💾
| Technology | Purpose |
|------------|---------|
| **Supabase** | PostgreSQL database with RPC functions for secure access |
| **Upstash Redis** | Job queue and ephemeral event streaming buffer |
| **Schema Isolation** | Multi-project database support with schema-qualified tables |

### **Deployment** 🚀
| Platform | Service |
|----------|---------|
| **Vercel** | Frontend hosting with edge functions |
| **Railway** | Backend API with auto-deployment |

---

## 🔄 How It Works

```
┌─────────────────────────────────────────────────────────────┐
│                    USER QUESTION                            │
│         "Explain quantum computing in simple terms"          │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              MULTI-AGENT SWARM ORCHESTRATION                │
│                                                             │
│  Round 1:                                                  │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │ Researcher   │  │   Critic     │  │  Explainer   │     │
│  │ • Analyzes    │→ │ • Reviews    │→ │ • Synthesizes│     │
│  │ • Identifies │  │ • Identifies │  │ • Structures │     │
│  │   key facts  │  │   gaps       │  │   explanation│     │
│  └──────────────┘  └──────────────┘  └──────┬───────┘     │
│                                             │               │
│                                    ┌────────▼────────┐      │
│                                    │  Summarizer     │      │
│                                    │ • Consolidates  │      │
│                                    │ • Resolves      │      │
│                                    │   contradictions│      │
│                                    └────────┬────────┘      │
│                                             │               │
│  Round 2: (Refinement)                     │               │
│  Agents review and improve based on       │               │
│  previous round's insights                 │               │
└─────────────────────────────────────────────┼───────────────┘
                                              │
                                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    FINAL ANSWER                             │
│  • Polished, coherent response                             │
│  • Synthesizes all agent perspectives                       │
│  • Ready for user consumption                               │
│                                                             │
│  All agent messages streamed in real time via SSE          │
└─────────────────────────────────────────────────────────────┘
```

### **Architecture Highlights**

- **Event-Driven Design** — Events are the source of truth for streaming UI
- **Queue-Based Execution** — Redis-backed job queue for scalable processing
- **Dual Persistence** — Events stored in both Redis (streaming) and Supabase (permanent)
- **Async Orchestration** — Non-blocking agent execution with proper error handling
- **Context Management** — Intelligent transcript and partial output sharing between agents

---

## 🎨 User Experience

### **Transparency First**
Every agent's thought process is visible. You see:
- What the Researcher discovers
- What the Critic questions
- How the Explainer structures the answer
- How the Summarizer consolidates everything

This transparency builds trust and demonstrates the system's reliability.

### **Modern Interface**
- **Hero Section** — Video backgrounds with theme-aware switching (static on mobile)
- **Playground** — Interactive agent panels with real-time updates, markdown rendering, and citation display
  - Input positioned under header with darker borders for visibility
  - 10-character minimum requirement with real-time feedback
  - Run Performance metrics with real-time polling
  - Toast notifications for user feedback at every stage
- **Dashboard (Runs)** — Thread management with search, pagination (6 per page), and delete functionality
  - Automatic thread title generation from user messages
  - Beautiful confirmation dialogs for destructive actions
  - Export functionality (Markdown/JSON)
- **Analytics** — Performance metrics and agent insights with robust error handling
- **Compare** — Side-by-side thread comparison with dropdown selection, markdown rendering, and export
- **Mobile Experience** — Fully optimized with bottom navigation, hamburger menu, improved contrast, and responsive layouts

### **Performance**
- **Sub-2 Second Start** — Streaming begins almost immediately
- **Real-Time Updates** — SSE ensures minimal latency
- **Optimized Queries** — Efficient database access with RPC functions
- **Smart Caching** — Redis for ephemeral data and queue management

---

## 📖 User Guide

### Getting Started

1. **Ask a Question** — Enter your question in the playground
2. **Watch the Agents** — See each agent's response stream in real time
3. **Review the Answer** — Read the consolidated final response
4. **Explore Threads** — View past conversations in the dashboard
5. **Analyze Performance** — Check analytics for insights

### Understanding the Agents

| Agent | What They Do | Example Output |
|-------|-------------|----------------|
| **Researcher** | Analyzes question, identifies key facts and constraints | "Key considerations: quantum superposition, qubits, practical applications..." |
| **Critic** | Reviews for gaps, errors, and risks | "Missing: discussion of quantum decoherence challenges..." |
| **Explainer** | Creates structured, clear explanation | "## Quantum Computing Basics\n\n1. **Qubits** - Unlike classical bits..." |
| **Summarizer** | Consolidates into final answer | "Quantum computing uses qubits that can exist in multiple states simultaneously..." |

### Pro Tips

- **Be Specific** — Clear questions produce better results
- **Watch Citations** — Agent responses may include source URLs automatically extracted and displayed
- **Use Pagination** — Navigate through all your threads using the Previous/Next buttons
- **Explore Threads** — Continue conversations for deeper exploration
- **Check Analytics** — Monitor agent performance and system metrics
- **Export Results** — Save important conversations as Markdown or JSON for reference
- **Delete Old Threads** — Keep your dashboard clean by deleting threads you no longer need
- **Read Markdown** — Agent responses support rich formatting including code blocks, links, and headings

---

## 📊 Performance & Architecture

### System Design

- **Event-Driven Architecture** — Events power real-time UI updates
- **Queue-Based Processing** — Scalable job execution with Redis
- **Dual Persistence Strategy** — Redis for streaming, Supabase for permanence
- **Async Orchestration** — Non-blocking agent execution
- **Schema Isolation** — Multi-project database support

### Performance Metrics

| Metric | Value |
|--------|-------|
| **Streaming Latency** | < 2 seconds to first event |
| **Average Run Time** | 15-25 seconds (1 round for demo, configurable) |
| **Frontend Bundle** | Optimized with Next.js 16 and code splitting |
| **Mobile Performance** | 90+ Lighthouse score with video disabled on mobile |
| **API Response Time** | < 100ms for non-LLM endpoints |
| **Pagination** | 6 threads per page with efficient offset-based queries |
| **Citation Extraction** | Automatic URL detection from agent responses |
| **Toast Notifications** | Sub-second display with smart dismissal logic |

### Scalability Features

- **Horizontal Scaling Ready** — Worker pattern supports multiple instances
- **Efficient Database Access** — RPC functions for secure, optimized queries
- **Smart Caching** — Redis for ephemeral data and queue management
- **Rate Limiting** — Per-IP protection against abuse

---

## 🛡️ Security & Reliability

- ✅ **Input Validation** — Pydantic schemas for all API inputs
- ✅ **Rate Limiting** — Configurable per-IP limits
- ✅ **CORS Protection** — Configurable allowed origins
- ✅ **Schema Isolation** — Database schema separation for security
- ✅ **RPC Functions** — Secure database access without exposing schemas
- ✅ **Error Handling** — Comprehensive error handling with user-friendly messages
- ✅ **Environment Variables** — All secrets managed via env vars

---

## 🎯 What Makes This Impressive

### **Multi-Agent Systems Design**
The orchestration of four specialized agents working in harmony demonstrates deep understanding of:
- Agent role specialization and prompt engineering
- Context sharing and collaboration patterns
- Round-based refinement workflows
- Error handling and graceful degradation

### **Transparency & UX**
Real-time streaming of agent thoughts showcases:
- Advanced event-driven UI patterns with toast notifications
- Server-Sent Events (SSE) implementation with reconnection logic
- State management for complex async flows with React 19.2 transitions
- User experience design for AI transparency
- Markdown rendering for rich text formatting
- Citation extraction and display for source attribution
- Beautiful, accessible UI components with shadcn/ui
- Mobile-first responsive design with optimized touch targets

### **Modern Full-Stack Architecture**
The complete system demonstrates:
- **Frontend**: React 19.2 with Server Components, Suspense, and Transitions
- **Backend**: FastAPI with async/await patterns and proper error handling
- **Database**: PostgreSQL with RPC functions and schema isolation
- **Infrastructure**: Redis queuing, SSE streaming, and dual persistence
- **Deployment**: Production-ready setup on Vercel and Railway

### **Production-Ready Features**
Beyond MVP, the application includes:
- **Analytics Dashboard** — Comprehensive metrics with error handling and data normalization
- **Thread Search & Pagination** — Full-text search with 6 threads per page navigation
- **Export Functionality** — Markdown/JSON export from multiple locations (Dashboard, Playground, Compare)
- **Citation Extraction** — Automatic URL detection and display from agent responses
- **Markdown Rendering** — Rich text formatting in all chat messages
- **Toast Notifications** — Beautiful, centered toasts with thick borders and smart dismissal
- **Delete Functionality** — Permanent thread deletion with beautiful confirmation dialogs
- **Automatic Titles** — Thread titles generated from first user message
- **Run Performance Metrics** — Real-time duration, message counts, and agent activity with polling
- **Performance Monitoring** — Real-time metrics and analytics
- **Mobile-Optimized UI/UX** — Bottom navigation, hamburger menu, improved contrast, 44px+ touch targets
- **Theme System** — Complete light/dark mode with smooth transitions and semantic tokens
- **Error Handling** — Comprehensive error handling with user-friendly messages and graceful degradation

---

## 👨‍💻 Creator

**Derril Filemon**  
*AI Engineer & Fullstack Developer*

This project demonstrates proficiency in:
- 🤖 **AI/ML Integration** — Multi-agent orchestration, OpenAI API, prompt engineering, citation extraction
- ⚛️ **Modern React** — Next.js 16, React 19.2, Server Components, Suspense, Transitions, useTransition
- 🐍 **Python Backend** — FastAPI, async/await, Pydantic, error handling, event loop management
- 🎨 **UI/UX Design** — Responsive design, dark/light themes, mobile optimization, toast notifications, markdown rendering
- ☁️ **Cloud Architecture** — Supabase, Redis, Railway, Vercel, CORS configuration, environment management
- 📊 **Data Engineering** — PostgreSQL, RPC functions, schema design, pagination, full-text search
- 🔧 **DevOps** — CI/CD, environment management, production deployment, error monitoring
- 🎯 **Product Polish** — Attention to detail in UI/UX, error handling, user feedback, accessibility

---

## 🙏 Acknowledgments

- **[OpenAI](https://openai.com/)** — GPT-4o-mini API for intelligent agent responses (62.5% cheaper than GPT-4.1-mini)
- **[Supabase](https://supabase.com/)** — PostgreSQL database and RPC functions
- **[Upstash](https://upstash.com/)** — Redis for queuing and event streaming
- **[Railway](https://railway.app/)** — Backend API deployment
- **[Vercel](https://vercel.com/)** — Frontend hosting and edge functions
- **[shadcn/ui](https://ui.shadcn.com/)** — Beautiful, accessible component library
- **[Next.js](https://nextjs.org/)** — React framework with App Router
- **[FastAPI](https://fastapi.tiangolo.com/)** — Modern Python web framework

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">

[Live Demo](https://autogen-distributed-ai-chat-with-sw.vercel.app/) • 

Made with ❤️ and ☕ by [Derril Filemon](https://github.com/derril-tech)

</div>
