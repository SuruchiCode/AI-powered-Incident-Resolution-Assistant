# AI-powered Incident Resolution Assistant

## Overview

This project is an AI-powered assistant designed to help IT support teams resolve incident tickets faster and more accurately. It leverages historical ticket data, semantic search, and conversational AI to recommend solutions, retrieve similar incidents, and answer troubleshooting questions in natural language. The solution is modular, cloud-ready, and easily deployable on Microsoft Azure.

---
Screenshots:
![Screenshot 2025-06-05 181352](https://github.com/user-attachments/assets/c4326063-33a9-4913-b6e2-63ba45671690)

![Screenshot 2025-06-05 181233](https://github.com/user-attachments/assets/c3955810-aea0-498d-bf29-6251b8e15999)

![Screenshot 2025-06-05 181203](https://github.com/user-attachments/assets/7aa87810-d41d-4a6b-bb76-7b16cd0a70d2)



## Features

- **Semantic Search:** Find similar past incidents using vector embeddings and state-of-the-art language models.
- **Resolution Recommendation:** Get concise, step-by-step solutions for new incidents based on historical data.
- **Conversational Assistant:** Ask troubleshooting questions and receive AI-powered answers.
- **Interactive UI:** Streamlit-based chatbot interface for seamless agent interaction.
- **Cloud-Ready:** Easily containerized and deployable on Azure App Service, Azure Container Instances, or similar platforms.

---

## Architecture

![Solution Architecture Diagram] 
LINK- https://drive.google.com/file/d/1qB994BNbVXdT_y9QCEyufVXyVJgrHCJO/view?usp=sharing

**Architecture Highlights:**
- **Ingestion:** Historical ITSM data (CSV) processed with Python and Pandas.
- **Vectorization:** Sentence Transformers convert ticket data into embeddings.
- **Vector Database:** ChromaDB stores embeddings for semantic search.
- **LLM Integration:** Ollama (open-source LLM) powers natural language understanding and solution generation(model used phi3).
- **Backend:** FastAPI exposes RESTful APIs for recommendations, search, and Q&A.
- **Frontend:** Streamlit provides an easy-to-use chatbot UI for agents.
- **Azure-ready:** Components are containerized and compatible with Azure services.

---

## Technologies Used

- **Python:** Core language for backend, data processing, and ML integration
- **FastAPI:** High-performance web framework for backend APIs
- **Ollama:** Open-source large language model for conversational AI
- **Sentence Transformers:** For generating semantic embeddings of ticket data
- **ChromaDB:** Vector database for efficient similarity search
- **Streamlit:** Rapid UI development for the chatbot interface
- **Pandas:** Data cleaning and preparation

---

## Getting Started

### Prerequisites

- Python 3.9+
- [Ollama](https://ollama.com/) server running (for LLM)
- Docker (optional, for containerized deployment)
- (Recommended) Azure account for cloud deployment

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/SuruchiCode/AI-powered-Incident-Resolution-Assistant.git
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up historical ticket data**
   - Place your ITSM CSV file in the `data/` directory.

4. **Start ChromaDB and embedding model**
   - No separate ChromaDB server required; the app handles this.
   - Make sure you have enough memory to load the Sentence Transformer model.

5. **Run Ollama server**
   ```bash
   ollama serve
   ollama pull phi3
   ollama run phi3
   ```

6. **Start the FastAPI backend**
   ```bash
   uvicorn main:app --reload
   ```

7. **Run the Streamlit frontend**
   ```bash
   streamlit run chatbot.py
   ```

8. **Access the UI**
   - Open the Streamlit URL in your browser (usually `http://localhost:8501`).

---

## How to Deploy on Microsoft Azure

- **Containerize the app** using Docker.
- **Deploy containers** to Azure App Service or Azure Container Instances.
- **Store data** in Azure Blob Storage and use Azure OpenAI if available for LLM features.
- **Integrate** with Azure DevOps for CI/CD and monitoring.

---

## Example Usage

1. **Enter a new incident description:**  
   The assistant suggests probable resolutions.
2. **Search for similar incidents:**  
   Retrieve historical tickets related to the current issue.
3. **Ask troubleshooting questions:**  
   Get concise, AI-generated answers.

---

## License

[MIT License](LICENSE)

---

## Authors

- Suruchicodes(Suruchi Kumari)

---

## Acknowledgments

- Open-source community for Ollama, FastAPI, ChromaDB, and Sentence Transformers.
- Microsoft Azure for cloud platform support.
