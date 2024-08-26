# LangGraph Custom Research Agent with GPT-4o

This README provides instructions on how to build a custom research agent using LangGraph and GPT-4o. This agent can perform in-depth research on a given topic by leveraging multiple tools and APIs.

## Prerequisites

Before you begin, ensure you have the following installed:

- Python 3.8 or higher
- pip (Python package installer)
- OpenAI API key
- Pinecone API key (if using Pinecone for knowledge base)

## Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-repo/langgraph-research-agent.git
    cd langgraph-research-agent
    ```

2. **Install required packages:**

    ```bash
    pip install -r requirements.txt
    ```

3. **Set up environment variables:**

    ```bash
    export OPENAI_API_KEY=your_openai_api_key
    export PINECONE_API_KEY=your_pinecone_api_key
    ```

## Usage

### Setting Up the Knowledge Base

If you are using Pinecone for the knowledge base, you need to set up an index:

1. **Initialize Pinecone:**

    ```python
    import pinecone
    pinecone.init(api_key="your_pinecone_api_key")
    ```

2. **Create an index:**

    ```python
    pinecone.create_index("research-index", dimension=128)
    ```

### Running the Research Agent

1. **Configure the research task:**

    Edit the `task.json` file to specify the research query and other parameters:

    ```json
    {
        "query": "Your research query here",
        "model": "gpt-4o",
        "max_sections": 5
    }
    ```

2. **Run the agent:**

    ```bash
    python main.py
    ```

### Customizing the Agent

You can customize the agent by modifying the tools and workflows in the `main.py` file. Here are some key components:

- **Web Search Tool:** Uses SerpAPI to fetch search results.
- **ArXiv Paper Fetch Tool:** Retrieves abstracts from arXiv.
- **RAG Search Tool:** Searches within a custom knowledge base.

### Example Workflow

1. **Planning Stage:** The agent plans the research outline.
2. **Data Collection:** The agent collects data using various tools.
3. **Review and Revision:** The agent reviews and revises the collected data.
4. **Writing and Submission:** The agent compiles the final report.
5. **Publication:** The agent publishes the report in multiple formats (PDF, Docx, Markdown).

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.

---

Feel free to customize this README to better fit your specific project needs! If you have any questions or need further assistance, let me know.

Source: Conversation with Copilot, 26/8/2024
(1) GPT-4o Research Agent in LangGraph - Google Colab. https://colab.research.google.com/github/pinecone-io/examples/blob/master/learn/generation/langchain/langgraph/01-gpt-4o-research-agent.ipynb.
(2) LangGraph | GPT Researcher. https://docs.gptr.dev/docs/gpt-researcher/langgraph.
(3) A Quick Introduction to LangGraph for Building Agentic Workflows Using .... https://yubesmart.com/2024/08/06/a-quick-introduction-to-langgraph-for-building-agentic-workflows-using-gpt-4o-mini/.
(4) Create a ReAct agent. https://langchain-ai.github.io/langgraph/how-tos/create-react-agent/.
