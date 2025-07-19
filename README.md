# mise-en-place
LLM app creation framework
# mise-en-place-llm-extractor

A simple, reproducible, and robust Python solution for extracting structured information and summarizing multiple documents using Large Language Models (LLMs). This project is built on the principle of **"Mise en Place"** – ensuring all components are prepared, organized, and ready *before* execution, leading to clear, efficient, and reliable LLM-powered applications.

## ✨ Philosophy: The "Mise en Place" for LLM Apps

Just as a chef meticulously preps all ingredients and tools before cooking, this framework emphasizes:
1.  **Defining Your Output:** Knowing precisely what you want (the plated dish).
2.  **Ready Tools:** Having reliable services for core operations (pre-set ovens, sharp knives).
3.  **Prepared Units:** Processing individual inputs into a usable form (chopped vegetables, measured spices).
4.  **Orchestrated Flow:** Coordinating all prepared elements for efficient, simultaneous execution (the chef's coordinated cooking plan).

This approach provides full control and transparency, avoiding the "black box" nature of some larger frameworks.

## 🚀 Features (Revised)

* **Structured Output with Pydantic:** Define precise data schemas for reliable, validated JSON output from the LLM.
* **Asynchronous Processing:** Leverage `asyncio` and `httpx` for concurrent API calls, significantly accelerating batch processing.
* **Robust LLM Interaction:**
    * **Automated Retries:** Implements exponential backoff for transient API errors, improving resilience.
    * **Output Repair Logic:** Attempts to guide the LLM to correct malformed JSON output if initial validation fails.
* **Cost Control & Safety:**
    * **Input Validation:** Enforces maximum document length to prevent excessive token consumption.
    * **Client-Side Rate Limiting:** Controls the concurrency of LLM calls to prevent hitting API rate limits.
* **Enhanced Observability:** Utilizes Python's `logging` module for better monitoring and debugging.
* **Modular Design:** Code separated into logical, reusable components for easy understanding and maintenance.
* **LLM Agnostic Core:** Easily adapt to different LLM providers (OpenAI, Google Gemini, Anthropic, etc.) by modifying a single service file.
* **Explicit Data Flow:** Clear passing of data between functions, enhancing traceability and debugging.
* **Comprehensive Error Handling:** Catches and reports various errors, including network issues, API errors, and data validation failures.

## 📋 Prerequisites

* Python 3.8+
* Internet connection for LLM API access.
* An API key for your chosen LLM (e.g., OpenAI).
    * **For OpenAI:** You'll need an `OPENAI_API_KEY`.
    * **To adapt for other LLMs:** You'll need to adjust the `call_llm_api` function in `src/llm_service.py` to match their API endpoints and request formats.

## ⚙️ Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/mise-en-place-llm-extractor.git](https://github.com/your-username/mise-en-place-llm-extractor.git)
    cd mise-en-place-llm-extractor
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows:
    .\venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## 🔑 Configuration (API Key & Settings)

**Important:** Never hardcode your API key directly into your code or commit it to version control!

We recommend setting your API key as an environment variable.

**On Linux/macOS:**
```bash
export OPENAI_API_KEY="YOUR_ACTUAL_OPENAI_API_KEY"
