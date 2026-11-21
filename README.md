Kumkim: An Autonomous Desktop Companion AI (Documentation Archive)

 IMPORTANT NOTICE: The source code for this project has been lost. This repository serves as a documentation archive. It contains the complete academic end-of-year project report (PDF), architectural designs, and a detailed breakdown of the system's implementation as originally developed. It is preserved here to showcase the architectural vision, system design, and engineering methodology applied.

 About the Project
Kumkim is an autonomous, desktop companion AI for Windows. Unlike traditional chatbots (which are stateless tools that only respond when spoken to), Kumkim is designed to feel alive. It lives in the system tray, possesses a randomly generated "Big-Five" temperament, maintains a continuous emotional state, remembers through a human-like decaying memory system, and possesses genuine autonomy—deciding on its own when to reach out or stay silent.

The entire system is built on a radical architectural principle: "LLM = judgment · Python = plumbing · CSS = display." No developer-written formulas compute emotion or trust. Instead, an invisible tag protocol allows the LLM to rewrite its own inner state after every message.

 Core Features
The Living Core: A neural voice whose pace and pitch are colored by the AI's current emotional state. It features a 7-value "soul state" that evolves turn-by-turn.

Human-Like Memory: Implements the Ebbinghaus forgetting curve. Memories decay over time, strengthen upon recall, and undergo a nightly "sleep" consolidation process.

Proactive Autonomy: A background "heartbeat" scheduler allows Kumkim to initiate contact, ask check-in questions, and set its own wake-up times.

Real-World Actions (The Senses): Directly controls YouTube Music, fetches weather, performs web searches, and even acts as a WhatsApp Secretary—relaying incoming messages and drafting/sending replies on the user's behalf.

Zero-Friction Capture: Automatically extracts calendar events, deadlines, and goals from natural conversation.

Privacy by Construction: 100% local data storage (SQLite and JSON). Operates entirely on free-tier APIs (Groq, Gemini) and keyless services (wttr.in, DuckDuckGo) ensuring zero running costs.

 Technical Architecture & Stack
The project was developed using Scrum methodology across three sprints, resulting in a highly robust system.

Frontend / Interface: PyQt6, QML/CSS (2,300 lines for the web-like interface), HTML/CSS for internal rendering.

Backend / Core Logic: Python (11,000 lines across 13 packages).

Database: SQLite (for structured data) and atomic JSON stores (for state persistence).

AI / LLM Integration: Groq, Google Gemini (utilizing multiple daily free quotas for load balancing).

Messaging Bridge: Node.js (whatsapp-web.js).

External APIs: YTMDesktop (local REST/socket API), wttr.in (weather), DuckDuckGo/Wikipedia (search).

Testing: unittest (114 automated offline tests passing).

 The "Tag Protocol" (Innovation)
Instead of writing Python if/else statements to guess how the AI should feel, Kumkim uses an invisible tag protocol. After the visible text reply, the LLM outputs hidden machine-readable tags (e.g., [MOOD: happy], [MEMORY: user likes jazz]). The Python layer merely parses, validates, and stores this data.

 What's Inside This Repository
📄 Kumkim_PFF_Report.pdf: The complete, official 50+ page academic project report (French/English) submitted to IMSET. It includes the full use case diagrams, class diagrams, sequence diagrams, and sprint backlogs.

 README.md: This document.

 My Contributions & Scope
As an individual end-of-year project (Second Year, Web Development Program at IMSET under the supervision of Mrs. Aness Bouaoud), I held all development roles. My work included:

Designing the multi-tier memory decay algorithm based on the Ebbinghaus curve.

Implementing the asynchronous "Heartbeat" scheduler that allows the AI to act proactively.

Developing the WhatsApp Node.js bridge and integrating it securely with the Python core.

Architecting the tag-parsing system to translate LLM output into persistent state changes.

Writing the 114-test offline suite to ensure robustness against live API failures.

 Why the Source Code is Missing
This project was developed entirely on a local machine during the academic year. Due to a hardware failure, the local repository and its backups were lost before it could be pushed to a remote server.

This repository acts as a testament to the engineering work. It demonstrates the ability to design complex, multi-threaded, API-integrated desktop applications from scratch.

See Also
My other active projects — Including my latest real-time full-stack web applications (React + TypeScript + Supabase).

Note: If you are a recruiter or developer reviewing this, feel free to read the attached PDF report to see the detailed sequence diagrams, class architectures, and sprint planning that went into this 11,000-line system.
 [Kumkim_PFF_Report.pdf](https://github.com/user-attachments/files/35215559/Kumkim_PFF_Report.pdf)
