
<img width="1024" height="1024" alt="Logo" src="https://github.com/user-attachments/assets/5a996d89-cca3-4b57-a6a7-19a99485af23" />


<img width="1916" height="1080" alt="App Page" src="https://github.com/user-attachments/assets/7a9cce1e-347d-41b6-8d40-357f74034e85" />

#  Live App Demo :-- 


https://github.com/user-attachments/assets/cfb0bac1-e54e-48df-bcbc-6b493a4f22db




# 🚀 **TechSeva AI Researcher**

### **Autonomous AI-Powered Research Agent for ArXiv Search, PDF Reading & Research Paper Generation**

🔗 **Live App:**
👉 [https://techseva-ai-researcher.streamlit.app/](https://techseva-ai-researcher.streamlit.app/)

---

# 🌟 **Overview**

**TechSeva AI Researcher** is an advanced **autonomous research assistant** that combines **LangGraph**, **Google Gemini**, **custom tools**, and a modern **Streamlit UI** to perform full research cycles:

✔ Search topics on **arXiv**
✔ Read and analyze **PDFs**
✔ Build a **knowledge graph**
✔ Draft research papers
✔ Export professional PDFs via **LaTeX**
✔ Generate audio summaries & Word exports

A complete AI research pipeline—inside your browser.

---

# 🎯 **Purpose**

* Provide an **AI-driven research assistant**
* Automate **literature review**
* Extract and summarize **PDF content**
* Generate full **research papers**
* Support **multiple languages**, personas, and critical analysis modes
* Export papers as **PDF and DOCX**

---

# 🖥️ **UI / Frontend (Streamlit — frontend.py)**

A clean, glassmorphism-themed interface with a **Sidebar Control Center**.

### Sidebar Controls:

* API Key (manual input, no `.env`)
* Model type
* Research depth (shallow → deep)
* Language (EN, ES, FR, DE, HI, CN, JP)
* Persona (Professor / Journalist / Skeptic / ELI5)
* Critical Review toggle
* Paper export & bookmarks

### UI Features:

* Real-time agent streaming
* Tool execution logs
* Chat interface with history replay
* Knowledge Graph (Graphviz)
* Audio summaries (gTTS)
* PDF & DOCX downloads
* Quick action buttons for research shortcuts

---

# 🤖 **AI Engine (LangGraph Agent — ai_researcher_2.py)**

The core research agent is built using **LangGraph**, powered by **Google Gemini** via `langchain-google-genai`.

### **Agent Flow**

* Load model with tools bound
* Conversation → detect tool calls
* Tool executes and returns data
* Agent continues with updated context
* Stops when final answer is achieved

### **Gemini Model**

`ChatGoogleGenerativeAI` with research-tuned prompts.

---

# 🛠️ **Custom Tools**

### 🔍 **1. ArXiv Search — arxiv_tool.py**

* Uses **arXiv Atom API**
* Parses XML → title, abstract, authors, categories, PDF link
* Returns structured search results

---

### 📄 **2. PDF Reader — read_pdf.py**

* Downloads PDF from arXiv link
* Extracts full text using **PyPDF2**
* Cleaned and chunked for analysis

---

### 📝 **3. LaTeX Paper Export — write_pdf.py**

* Generates `.tex`
* Renders PDF using **tectonic engine**
* Saves timestamped PDF in `output/`
* Returned for user download

---

# 🧠 **Key Features**

### ✔ **ArXiv Integrated Search**

Topic-based results
Fetch abstracts, authors, and direct PDF links

---

### ✔ **Deep PDF Understanding**

Extract full PDF text
Perform topic and structure analysis

---

### ✔ **Knowledge Graph Generation**

Graphviz-powered visualization of:

* Topics
* Concepts
* Linked papers
* Citation relationships

---

### ✔ **Autonomous Research Drafting**

AI writes full academic-style papers with:

* Abstract
* Background
* Literature review
* Analysis
* Conclusion
* References

---

### ✔ **Personas**

* 👨‍🏫 Professor
* 📰 Journalist
* ❓ Skeptic
* 🧒 ELI5

Changes writing tone and reasoning depth.

---

### ✔ **Multi-Language Output**

Supports 7 languages:
EN, ES, FR, DE, HI, CN, JP.

---

### ✔ **Critical Review Mode**

Adds:

* Weakness analysis
* Bias detection
* Limitations
* SWOT-style evaluations

---

### ✔ **Audio Summaries**

* gTTS generates long-form audio explanations
* Downloadable as `.mp3`

---

### ✔ **Word Export**

* Convert research outputs into `.docx`

---

### ✔ **Bookmarks & Stored Papers**

Saved generated papers with details for later download.

---

# 📦 **Data & State Handling**

Stored in Streamlit `session_state`:

* `api_key`
* `chat_history`
* `research_graph`
* `generated_papers`
* `bookmarks`

Knowledge graph expands dynamically when:

* Tools like arXivSearch run
* New topics discovered
* PDF content is read

---

# ⚙️ **Dependencies**

### **Core**

* langchain
* langchain-core
* langchain-google-genai
* langgraph
* typing-extensions

### **UI**

* streamlit
* graphviz

### **Tools**

* requests (arXiv API)
* PyPDF2 / pypdf
* python-docx
* gTTS

### **Build**

* tectonic (system-level installation)

---

# 🚀 **How to Run Locally**

### **1. Create Virtual Environment**

```bash
python -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows
```

### **2. Install Requirements**

```bash
pip install -r requirements.txt
```

### **3. Start Streamlit App**

```bash
streamlit run frontend.py
```

### **4. Enter Your Google API Key**

Inside sidebar → “Settings”.

---

# 🧭 **User Workflow**

### **1️⃣ Ask a research question**

→ Tool-triggered arXiv search

### **2️⃣ Browse retrieved papers**

→ PDFs are read & analyzed

### **3️⃣ Agent performs deep reasoning**

→ Creates topic map
→ Expands knowledge graph

### **4️⃣ AI drafts a research paper**

→ Persona + Language applied

### **5️⃣ Export**

* PDF (LaTeX)
* Word (DOCX)
* Audio Summary

---

# ⚠️ **Limitations**

* Requires **tectonic** installed for PDF export
* PDF reading depends on PyPDF2 (may fail on scanned PDFs)
* ArXiv API rate limits
* Knowledge graph is heuristic, not vector-based
* No persistent storage (session memory only)

---

# 💡 **Future Enhancements**

* Cloud persistent knowledge base
* Fine-tuned scholarly models
* Automatic citation formatting
* Cross-paper linking and reasoning
* Multi-PDF batch analysis

---


---

# 🌳 **TechSeva AI Researcher – LangGraph Binary Tree Workflow**

```
                                      ┌──────────────────────────────┐
                                      │        USER INPUT            │
                                      │  (Research Query / Topic)    │
                                      └───────────────┬──────────────┘
                                                      │
                                                      ▼
                                      ┌──────────────────────────────┐
                                      │    SYSTEM PROMPT BUILDER     │
                                      │  (persona + language + depth │
                                      │   + critical review + style) │
                                      └───────────────┬──────────────┘
                                                      │
                                                      ▼
                                   ┌──────────────────────────────────────────┐
                                   │           LANGGRAPH AGENT NODE           │
                                   │  Gemini LLM + Tool Routing + Memory      │
                                   └───────────────────┬──────────────────────┘
                                                       │
                 ┌─────────────────────────────────────┼─────────────────────────────────────┐
                 ▼                                     ▼                                     ▼
   ┌───────────────────────┐              ┌────────────────────────┐          ┌───────────────────────────┐
   │  TOOL CALL DETECTOR   │              │   DIRECT RESPONSE       │          │   CRITICAL ANALYSIS       │
   │ Does agent need a     │              │ If no tools needed,     │          │ If enabled, SWOT-based     │
   │ tool? (Yes/No)        │──No────────▶│ respond instantly        │          │ reasoning added            │
   └───────────┬───────────┘              └────────────────────────┘          └───────────────────────────┘
               │Yes
               ▼
   ┌──────────────────────────┐
   │   TOOL ROUTER / BRANCH   │
   │ Agent selects the tool   │
   └───────────┬──────────────┘
               │
               │
   ┌───────────┼────────────────────────────────────────────────────────────────────────────┐
   ▼           ▼                                      ▼                                     ▼
┌───────────────────────┐               ┌────────────────────────┐            ┌──────────────────────────────┐
│ ARXIV_SEARCH TOOL      │               │  PDF_READER TOOL       │            │   WRITE_PDF TOOL (LaTeX)     │
│ Query → XML → Parsed   │               │ Downloads PDF → text   │            │ Render LaTeX → Tectonic →PDF │
│ entries + graph nodes  │               │ extraction             │            │   return PDF path            │
└───────────┬────────────┘               └──────────┬────────────┘            └────────────┬────────────────┘
            │                                         │                                     │
            │                                         │                                     │
            └─────────────────────────────┬───────────┴───────────────────────┬─────────────┘
                                          ▼                                   ▼
                       ┌──────────────────────────┐              ┌──────────────────────────┐
                       │   TOOL RESULT MERGER     │              │  KNOWLEDGE GRAPH UPDATE  │
                       │ Results merged into       │              │ Nodes + edges expanded   │
                       │ state for next LLM step   │              │ by tool outputs          │
                       └──────────────┬────────────┘              └─────────────┬────────────┘
                                      │                                           │
                                      └──────────────────────────────┬────────────┘
                                                                     ▼
                                          ┌───────────────────────────────────────────────┐
                                          │   AGENT LOOP (LangGraph Conditional Step)     │
                                          │ Check: Are more tools needed? (Yes/No)         │
                                          └────────────────────┬───────────────────────────┘
                                                               │
                                                    ┌──────────┘
                                                    ▼
                                     ┌──────────────────────────────────────────┐
                                     │       FINAL RESEARCH OUTPUT NODE        │
                                     │  – Draft Paper                           │
                                     │  – Summary                               │
                                     │  – Literature Review                     │
                                     │  – Critical Review (if enabled)          │
                                     └───────────────────┬──────────────────────┘
                                                         │
                                                         ▼
                                    ┌──────────────────────────────────────────────┐
                                    │ STREAMLIT UI (frontend.py) OUTPUT HANDLERS │
                                    └───────────────────┬─────────────────────────┘
                                                        │
                           ┌────────────────────────────┼──────────────────────────────────────────────────────────┐
                           ▼                            ▼                           ▼                            ▼
           ┌─────────────────────────┐   ┌─────────────────────────────┐   ┌──────────────────────────┐   ┌───────────────────────────┐
           │ PDF Download (LaTeX)    │   │  DOCX Export (python-docx) │   │ Audio Summary (gTTS)     │   │ Knowledge Graph (Graphviz) │
           └─────────────────────────┘   └─────────────────────────────┘   └──────────────────────────┘   └───────────────────────────┘

```

---

# ✔ **Binary Tree Explanation (Short Version)**

```
USER INPUT
 └── SYSTEM PROMPT BUILDER
      └── LANGGRAPH AGENT
           ├── Direct Answer (no tools)
           └── Tool Router
                ├── arxiv_search
                ├── read_pdf
                └── write_pdf
           → Merge results
           → Loop again if needed
           → Final Output
           → Streamlit UI (PDF, DOCX, Audio, Graph)
```

---

## ❤️ **Made with Passion by Abhishek Yadav & Open-Source Contributors!** 🚀✨


<h1 align="center">© LICENSE <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Check%20Box%20With%20Check.webp" alt="Check Box With Check" width="25" height="25" /></h1>

<table align="center">
  <tr>
     <td>
       <p align="center"> <img src="https://github.com/malivinayak/malivinayak/blob/main/LICENSE-Logo/MIT.png?raw=true" width="80%"></img>
    </td>
    <td> 
      <img src="https://img.shields.io/badge/License-MIT-yellow.svg"/> <br> 
This project is licensed under <a href="./LICENSE">MIT</a>. <img width=2300/>
    </td>
  </tr>
</table>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="900">




 <hr>

<div align="center">
<a href="#"><img src="assets/githubgif.gif" width="150"></a>
	
### **Thanks for checking out my GitHub Profile!**  

 ## 💌 Sponser

  [![BuyMeACoffee](https://img.buymeacoffee.com/button-api/?text=Buymeacoffee&emoji=&slug=codingstella&button_colour=FFDD00&font_colour=000000&font_family=Comic&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/abhishekkumar62000)

## 👨‍💻 Developer Information  
**Created by:** **Abhishek Kumar**  
**📧 Email:** [abhiydv23096@gmail.com](mailto:abhiydv23096@gmail.com)  
**🔗 LinkedIn:** [Abhishek Kumar](https://www.linkedin.com/in/abhishek-kumar-70a69829a/)  
**🐙 GitHub Profile:** [@abhishekkumar62000](https://github.com/abhishekkumar62000)

<p align="center">
  <img src="https://github.com/user-attachments/assets/6283838c-8640-4f22-87d4-6d4bfcbbb093" width="120" style="border-radius: 50%;">
</p>
</div>  


`Don't forget to give A star to this repository ⭐`


`👍🏻 All Set! 💌`

</div>

---

