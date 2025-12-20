# 🧠 SwarmChat
**Distributed AI Chat with Multi-Agent Architecture**

🌐 **[View Live Application](https://autogen-distributed-ai-chat-with-sw.vercel.app/)**

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
- **Mobile-Optimized** — Responsive design with 44px+ touch targets and mobile navigation
- **Hero Video Backgrounds** — Immersive landing experience with theme-aware videos
- **Interactive Analytics** — Dashboard with thread search, statistics, and performance metrics

### 📊 **Rich Feature Set**
| Feature | Description |
|---------|-------------|
| 🎯 **Real-Time Streaming** | SSE-based event streaming for live agent updates |
| 📝 **Thread Management** | Create, list, search, and revisit conversation threads |
| 📈 **Analytics Dashboard** | Comprehensive statistics and agent performance metrics |
| 🔍 **Thread Search** | Full-text search across thread titles and content |
| 📤 **Export Functionality** | Download threads as Markdown or JSON |
| 📊 **Run Performance Metrics** | Duration, message counts, and agent activity breakdown |
| 🔄 **Thread Comparison** | Side-by-side comparison of different conversations |
| 📱 **Mobile Navigation** | Bottom nav and hamburger menu for seamless mobile UX |
| 🎨 **Theme System** | Complete light/dark mode with smooth transitions |
| 💾 **Full Persistence** | All conversations saved to Supabase PostgreSQL |

---

## 🏗️ Tech Stack

### **Frontend** ⚛️
| Technology | Purpose |
|------------|---------|
| **Next.js 16.0.10** | React framework with App Router and Server Components |
| **React 19.2** | Latest React with concurrent features and transitions |
| **TypeScript** | Type-safe development with strict mode |
| **Tailwind CSS** | Utility-first styling with custom design system |
| **shadcn/ui** | Beautiful, accessible component library |
| **Server-Sent Events** | Real-time event streaming from backend |

### **Backend** 🐍
| Technology | Purpose |
|------------|---------|
| **FastAPI** | High-performance async Python API framework |
| **OpenAI GPT-4.1-mini** | Advanced language model for agent responses |
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
- **Hero Section** — Video backgrounds with theme-aware switching
- **Playground** — Interactive agent panels with real-time updates
- **Dashboard** — Thread management with search and statistics
- **Analytics** — Performance metrics and agent insights
- **Mobile Experience** — Fully optimized with bottom navigation and responsive layouts

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
- **Use Multiple Rounds** — Default 2 rounds allow agents to refine their work
- **Explore Threads** — Continue conversations for deeper exploration
- **Check Analytics** — Monitor agent performance and system metrics
- **Export Results** — Save important conversations for reference

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
| **Average Run Time** | 20-30 seconds (2 rounds) |
| **Frontend Bundle** | Optimized with Next.js 16 |
| **Mobile Performance** | 90+ Lighthouse score |
| **API Response Time** | < 100ms for non-LLM endpoints |

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
- Advanced event-driven UI patterns
- Server-Sent Events (SSE) implementation
- State management for complex async flows
- User experience design for AI transparency

### **Modern Full-Stack Architecture**
The complete system demonstrates:
- **Frontend**: React 19.2 with Server Components, Suspense, and Transitions
- **Backend**: FastAPI with async/await patterns and proper error handling
- **Database**: PostgreSQL with RPC functions and schema isolation
- **Infrastructure**: Redis queuing, SSE streaming, and dual persistence
- **Deployment**: Production-ready setup on Vercel and Railway

### **Production-Ready Features**
Beyond MVP, the application includes:
- Analytics dashboard with comprehensive metrics
- Thread search and filtering
- Export functionality (Markdown/JSON)
- Performance monitoring
- Mobile-optimized UI/UX
- Theme system with smooth transitions

---

## 👨‍💻 Creator

**Derril Filemon**  
*AI Engineer & Fullstack Developer*

This project demonstrates proficiency in:
- 🤖 **AI/ML Integration** — Multi-agent orchestration, OpenAI API, prompt engineering
- ⚛️ **Modern React** — Next.js 16, React 19.2, Server Components, Suspense
- 🐍 **Python Backend** — FastAPI, async/await, Pydantic, error handling
- 🎨 **UI/UX Design** — Responsive design, dark/light themes, mobile optimization
- ☁️ **Cloud Architecture** — Supabase, Redis, Railway, Vercel
- 📊 **Data Engineering** — PostgreSQL, RPC functions, schema design
- 🔧 **DevOps** — CI/CD, environment management, production deployment

---

## 🙏 Acknowledgments

- **[OpenAI](https://openai.com/)** — GPT-4.1-mini API for intelligent agent responses
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

**⭐ Star this repo if you find it useful!**

[Live Demo](https://autogen-distributed-ai-chat-with-sw.vercel.app/) 

Made with ❤️ and ☕ by [Derril Filemon](https://github.com/derril-tech)

</div>
