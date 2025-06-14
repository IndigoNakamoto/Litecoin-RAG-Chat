# Project Roadmap: Litecoin Knowledge Hub

## Project Scope & Objectives
A RAG (Retrieval-Augmented Generation) Chatbot for Litecoin users is an AI-powered conversational tool that provides real-time, accurate answers about Litecoin by retrieving relevant data from verified sources. It aims to solve the problem of misinformation and scattered resources by offering a centralized, reliable way for users to access Litecoin-related information, such as transactions, wallet management, and market insights. This will enhance user experience and foster greater adoption of Litecoin.

*   Establish and maintain a canonical, human-vetted knowledge base managed through Ghost CMS that serves as the single source of truth for the RAG pipeline, ensuring the highest level of accuracy and clarity while enabling Foundation-controlled editorial workflows.

## Strategic Value Proposition: Specialist vs. Generalist AI

This project's value is not in competing with general-purpose AI models like ChatGPT or Grok, but in providing a specialized, high-accuracy information utility for the Litecoin ecosystem. Generalist models, while powerful, are not suitable for tasks requiring real-time, verifiable data from trusted sources.

Our RAG-based approach provides a distinct advantage by:

1.  **Ensuring Data Accuracy:** We retrieve information from a curated set of live data sources (e.g., blockchain APIs, market data, official documentation), mitigating the risk of AI "hallucinations."
2.  **Providing Real-Time Information:** Unlike the static knowledge of general models, our system can query live data for features like transaction lookups and current market prices.
3.  **Delivering Verifiable Trust:** Our responses are grounded in specific, trusted data sources managed through professional editorial workflows in Ghost CMS, providing a level of reliability that is essential for financial and technical queries.

This focus on specialized, real-time, and accurate data is the core differentiator that makes the Litecoin RAG Chat a valuable and necessary tool for its target audience.

## Key Features & User Stories
*   **Primary Goal(s):**
    *   Deliver accurate, real-time responses to Litecoin-related queries using open-source data like blockchain records, market APIs, and community resources.
    *   Simplify user access to Litecoin information, reducing reliance on fragmented or unverified sources.
    *   Increase user engagement and trust in the Litecoin ecosystem through reliable, conversational support.
*   **Target Users/Audience:**
    *   Litecoin users (novice and experienced)
    *   Cryptocurrency enthusiasts
    *   Developers building on Litecoin
    *   Potential adopters seeking reliable information about Litecoin's features, transactions, or market trends.
*   **Core Features (MVP/Phase 1):**
    *   **Feature 1: Litecoin Basics & FAQ**
        *   Description: Provides clear, concise answers to fundamental questions about Litecoin, its history, how it works, and common terminology. Caters especially to new users.
        *   Example Queries: "What is Litecoin?", "How is Litecoin different from Bitcoin?", "How do I get a Litecoin wallet?"
    *   **Feature 2: Transaction & Block Explorer**
        *   Description: Allows users to look up details of Litecoin transactions (e.g., status, confirmations, fees) using a transaction ID, and explore block information (e.g., height, timestamp, included transactions). Useful for all users, including developers.
        *   Example Queries: "Check status of transaction [TXID]", "What was in block [Block Height]?", "How many confirmations does transaction [TXID] have?"
    *   **Feature 3: Market Data & Insights**
        *   Description: Delivers real-time Litecoin price information, market capitalization, trading volume, and basic chart data from reliable market APIs.
        *   Example Queries: "What's the current price of Litecoin?", "Show me Litecoin's market cap.", "Litecoin price trend last 7 days."
    *   **Feature 4: Developer Documentation & Resources**
        *   Description: Provides quick access to snippets from Litecoin developer documentation, links to key resources, and answers to common technical questions for developers building on Litecoin.
        *   Example Queries: "How to use Litecoin RPC call [method_name]?", "Link to Litecoin improvement proposals (LIPs).", "What are common Litecoin scripting opcodes?"
    *   **Feature 5: Curated Knowledge Base**
        *   Description: A continuously updated library of well-researched, clearly written articles and data covering all aspects of Litecoin. This content is explicitly structured for optimal machine retrieval and serves as the primary source for the chatbot's answers. Content is managed through Ghost CMS with Foundation editorial oversight.
    *   **Feature 6: Ghost CMS Integration**
        *   Description: A robust content management solution leveraging Ghost CMS to ensure the quality, consistency, and accuracy of the Litecoin Knowledge Base. Ghost CMS provides enterprise-grade content management with native Markdown support, facilitating Foundation-controlled editorial workflows for content creation, review, and publishing.
        *   **Primary Goals:**
            *   **Foundation Editorial Control:** Implement Ghost's role-based system where community contributors create drafts and Foundation team controls publishing decisions.
            *   **Native Markdown Compatibility:** Leverage Ghost's built-in Markdown support for seamless integration with existing RAG pipeline hierarchical chunking.
            *   **Real-time Synchronization:** Establish webhook-based synchronization between Ghost CMS and RAG pipeline for immediate content updates.
            *   **Professional Content Management:** Provide Foundation team with enterprise-grade content creation, editing, and publishing tools.
        *   User Stories: Foundation editors can review and publish community-contributed content through Ghost's editorial interface, while the RAG pipeline automatically stays synchronized with published content changes.

*   **Phase 2: User Experience & Accuracy Enhancements (Planned)**
    *   **Trust & Transparency (Source Citations):** Implement in-line citations in AI responses, linking directly to retrieved source documents for verifiability.
    *   **Dynamic & Interactive Experience (Streaming & Suggestions):** Enable real-time streaming of AI responses for a faster feel, and generate proactive follow-up questions to guide user interaction.
    *   **Upgraded Retrieval Engine (Hybrid Search & Re-ranking):** Enhance document retrieval accuracy by combining vector similarity with keyword search (hybrid search) and re-ranking retrieved documents for optimal relevance.
    *   **User Feedback Loop:** Introduce a mechanism for users to provide direct feedback on AI answer quality, enabling continuous improvement and data collection.

## Architectural Overview & Patterns
*   The project utilizes a Next.js frontend, Python/FastAPI backend, and Ghost CMS for content management. The architecture is centered around a **content-first RAG pipeline** with Ghost CMS as the authoritative content source, where curated knowledge base content is managed through professional editorial workflows and automatically synchronized with the RAG system to provide context for the LLM, ensuring responses are grounded in verified, Foundation-approved information.

## Core Technology Decisions
*   (Summary, see `techStack.md` for details)
    *   Frontend: Next.js, Tailwind CSS
    *   Backend: Python, FastAPI
    *   Content Management: Ghost CMS (self-hosted), MySQL
    *   Vector Database: MongoDB Atlas Vector Search
    *   Content Processing: HTML-to-Markdown conversion, hierarchical chunking
    *   Embedding: Google Text Embedding 004
    *   Integration: Ghost Content API, webhooks
    *   Deployment: Vercel (frontend), TBD (backend), self-hosted (Ghost)

## Significant Constraints
*   Reliance on open-source data quality and availability.
*   Ghost CMS hosting and maintenance requirements.
*   Need for robust security for Ghost CMS access and webhook integrations.
*   Scalability to handle target user engagement while maintaining Ghost CMS performance.
*   Foundation team capacity for content review and editorial workflows.

## High-Level Security Requirements & Standards
*   Input validation for all user queries and webhook payloads.
*   Protection against common web vulnerabilities (OWASP Top 10).
*   Secure handling of API keys for Ghost CMS and external services.
*   Ghost CMS security best practices (SSL, regular updates, secure hosting).
*   Webhook signature verification for Ghost-to-RAG synchronization.
*   Role-based access control in Ghost CMS aligned with Foundation governance.

## Major Milestones & Tentative Timelines
*   **Milestone 1:** Project Initialization & Documentation Setup (Completed)
*   **Milestone 2:** Basic Project Scaffold (Next.js Frontend, FastAPI Backend) (Completed)
*   **Milestone 3:** Core RAG Pipeline Implementation (Data Ingestion, Embedding, Retrieval, Generation) (Completed)
*   **Milestone 4:** MVP Feature 1 Implementation (Litecoin Basics & FAQ) (Completed)
*   **Milestone 5:** MVP Feature 2 Implementation (Transaction & Block Explorer) (Planned)
*   **Milestone 6: Ghost CMS Integration** ([View Details](./milestones/milestone_6_ghost_cms_integration.md))
    *   **Phase 1: Planning & Infrastructure Setup (`GHOST-INT-001`)** - ✅ Completed
        *   **Goal:** Research Ghost CMS compatibility, plan integration architecture, and set up Ghost CMS infrastructure.
        *   **Tasks:** Conduct Ghost CMS evaluation against project requirements, design integration architecture, provision Ghost hosting environment, configure initial Ghost instance with Content API access.
    *   **Phase 2: Content API Integration & Webhook Synchronization (`GHOST-INT-002`)** - ⏳ In Progress
        *   **Goal:** Implement seamless integration between Ghost CMS and existing RAG pipeline.
        *   **Tasks:** Develop Ghost Content API client, create `embedding_processor_ghost.py` for HTML-to-Markdown conversion and hierarchical chunking, implement webhook endpoints for real-time content synchronization, establish content metadata mapping between Ghost and RAG systems.
    *   **Phase 3: Content Migration & Editorial Workflow Setup (`GHOST-INT-003`)** - 📝 Planned
        *   **Goal:** Migrate existing knowledge base to Ghost and establish Foundation editorial workflows.
        *   **Tasks:** Migrate legacy Markdown content from `knowledge_base/` to Ghost CMS, configure Ghost user roles and permissions for Foundation team and community contributors, establish content review and publishing workflows, train Foundation team on Ghost editorial features.
    *   **Phase 4: Advanced Features & Optimization (`GHOST-INT-004`)** - 📝 Planned
        *   **Goal:** Implement advanced Ghost CMS features and optimize performance.
        *   **Tasks:** Integrate AI-assisted authoring tools through Ghost's extensibility, implement advanced content templates and structured data, optimize Ghost-to-RAG synchronization performance, establish monitoring and analytics for content management workflows.
*   **Milestone 7:** MVP Feature 4 Implementation (Developer Documentation & Resources) ([View Details](./milestones/milestone_7_developer_documentation.md)) (Planned)
*   **Milestone 8:** Testing, Refinement & Deployment ([View Details](./milestones/milestone_8_testing_refinement_deployment.md)) (Planned)
*   **Milestone 9:** MVP Feature 3 Implementation (Market Data & Insights) ([View Details](./milestones/milestone_9_market_data_insights.md)) (Planned)
*   (Timelines to be determined)

## Success Metrics
*   Achieve an average user engagement of 10,000 queries per week within 6 months of launch.
*   Process at least 1,000 unique transaction-related queries per day with 95% accuracy.
*   Attain a user satisfaction rating of 4.5/5 based on post-interaction surveys.
*   Maintain content freshness with 90% of knowledge base articles updated within 30 days of relevant Litecoin ecosystem changes.
*   Achieve 95% uptime for both chatbot interface and Ghost CMS editorial system.

## Completion Criteria
*   All MVP features (1-6) successfully deployed and operational.
*   Ghost CMS fully integrated with automated RAG pipeline synchronization.
*   Foundation editorial workflow established and operational in Ghost CMS.
*   Complete knowledge base migrated to Ghost with proper content organization.
*   Comprehensive monitoring and analytics systems in place.
*   User feedback collection and iteration mechanisms operational.

## Log of Completed Major Milestones/Phases
*   **Milestone 1: Project Initialization & Documentation Setup** - Completed 6/5/2025
    *   Initial `cline_docs` created and populated.
*   **Milestone 2: Basic Project Scaffold (Next.js Frontend, FastAPI Backend)** - Completed 6/5/2025
    *   Frontend (Next.js) and Backend (FastAPI) directory structures established.
    *   Basic "Hello World" functionality confirmed for both.
*   **Milestone 3: Core RAG Pipeline Implementation** - Completed 6/6/2025
    *   **Data Ingestion Framework:** Implemented and tested multi-source data loaders (Markdown, GitHub, Web).
    *   **Embedding:** Integrated Google Text Embedding 004.
    *   **Vector Store:** Set up and integrated MongoDB Atlas Vector Search.
    *   **Retrieval:** Implemented document retrieval based on similarity search.
    *   **Generation:** Integrated Langchain with `ChatGoogleGenerativeAI` (gemini-pro) to generate answers from retrieved context.
    *   **API:** `/api/v1/chat` endpoint created and functional, returning both the generated answer and source documents for transparency.
    *   **Testing:** Standalone test script (`backend/test_rag_pipeline.py`) created to validate the end-to-end pipeline.
    *   The core RAG pipeline is now functional and capable of ingesting data, retrieving relevant chunks, and generating answers with source attribution.
    *   **Enhancement (6/6/2025):** The RAG pipeline was significantly enhanced by implementing hierarchical chunking for Markdown, specific `task_type` usage for `text-embedding-004` (distinguishing between document and query embeddings), and an improved LLM prompt template. These changes optimize retrieval accuracy and contextual understanding.
    *   **Enhancement (6/6/2025):** Implemented metadata filtering capabilities. This involved updating `embedding_processor.py` to parse frontmatter (including `published_at` date conversion), `vector_store_manager.py` to handle flattened metadata for deletion, and confirming the correct Atlas Vector Search index definition for filtering on root-level fields.
*   **Milestone 4: Backend & Knowledge Base Completion (MVP Feature 1: Litecoin Basics & FAQ)** - Completed 6/7/2025
    *   **Data Source CRUD API:** Implemented a full suite of CRUD API endpoints (`/api/v1/sources`) for managing data sources, providing a foundational mechanism for controlling the knowledge base.
    *   **Full Knowledge Base Ingestion:** Successfully ingested and validated the entire (initial 7 articles and 4 deep research articles) knowledge base, including `articles` and `deep_research` content, resolving multiple bugs in the process.
    *   **Advanced Metadata Filtering:** Enhanced the vector search index to support filtering on all available metadata fields, enabling more powerful and granular queries.
    *   With these tasks completed, the entire backend and data pipeline for the MVP FAQ feature is now functional and validated.
*   **Milestone 6: Ghost CMS Integration - Phase 1: Planning & Infrastructure Setup (`GHOST-INT-001`)** - Completed 6/12/2025
    *   **Ghost CMS Evaluation:** Conducted comprehensive assessment of Ghost CMS compatibility with project requirements, including RAG pipeline integration, RBAC capabilities, and Foundation governance needs.
    *   **Architecture Planning:** Designed integration architecture leveraging Ghost Content API and webhooks for real-time synchronization with existing RAG pipeline.
    *   **Infrastructure Requirements:** Defined hosting requirements, database architecture (MySQL for Ghost, MongoDB for vectors), and deployment strategies.
    *   **Strategic Decision:** Confirmed Ghost CMS as optimal solution for Foundation-controlled editorial workflows while maintaining excellent RAG compatibility through native Markdown support.
    *   This milestone represents the strategic pivot from custom CMS development to Ghost CMS integration, significantly accelerating development timeline while providing enterprise-grade content management capabilities.
