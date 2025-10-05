🧠 Company Website Brochure Generator
This project automatically scrapes a company’s website, extracts relevant information (like “About,” “Careers,” “Products,” etc.), and uses a local Ollama LLM (e.g., llama3.2) to generate a company brochure in Markdown format.
🚀 Features

Scrapes webpages and subpages using requests and BeautifulSoup.
Automatically filters relevant links (e.g., About, Products, Careers).
Integrates with Ollama to summarize and create a polished company brochure.
Supports streamed generation for live token-by-token output.
Outputs the final brochure in Markdown format.

🧩 Requirements
Python Libraries
Install dependencies:
pip install requests beautifulsoup4 ipython

Ollama Setup

Install Ollama (must be running locally).
Make sure the model llama3.2 (or any preferred one) is installed:ollama pull llama3.2


Verify Ollama is running:curl http://localhost:11434/api/generate -d '{"model":"llama3.2","prompt":"Hello"}'



⚙️ Configuration
You can modify the configuration in the script:
OLLAMA_URL = "http://localhost:11434/api/generate"
MODEL = "llama3.2"

Change these values if using a different model or remote server.
🧠 How It Works

Website Scraping: Fetches the landing page, extracts visible text, and gathers links.
Link Selection: The model classifies which links are relevant for a brochure.
Content Extraction: Retrieves content from relevant pages.
Brochure Generation: Sends the extracted content to the model to create a concise, Markdown-formatted company brochure.

🧪 Usage
Run the script directly:
python brochure_generator.py

By default, it runs:
stream_brochure("Hugging Face", "https://huggingface.co")

You can modify the target:
stream_brochure("OpenAI", "https://openai.com")

📄 Example Output
# OpenAI Brochure

**About Us**  
OpenAI is an AI research company focused on developing safe and beneficial artificial intelligence...

**Careers**  
We’re hiring across engineering, research, and policy...

**Products**  
ChatGPT, Codex, and DALL·E are examples of our AI tools for productivity and creativity.

⚠️ Notes

Some sites may block scraping (use headers responsibly).
Ensure the Ollama server is active before running.
Large pages may be truncated to fit prompt limits (first 5000 chars).

🧑‍💻 Author
Created by: Mariem Aissa