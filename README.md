News Generation using LangChain and OpenAI
This repository contains a Python script designed to search for news articles, process their contents, and generate key points and summaries using OpenAI's GPT-4 model. The script leverages several tools, including a custom-built database for storing and retrieving news articles, and integrates with external services like NewsAPI and DuckDuckGo for web searches.

Prerequisites
Before running the script, ensure you have the following:

Python 3.10 or higher: The script is designed to work with Python 3.10+.
API Keys:
OpenAI API Key: Required for accessing OpenAI's GPT-4 model.
NewsAPI Key: Required for fetching news articles.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/aki83reo/news-generation-crewai.git
cd news-generation-crewai
Set up a Python virtual environment:

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install required packages:

bash
Copy code
pip install -r requirements.txt
Set up environment variables:

Add your API keys to your environment variables:
bash
Copy code
export NEWSAPI_KEY="your_newsapi_key"
export OPENAI_API_KEY="your_openai_api_key"
Usage
Overview of the Script
Tool 1: Search and Store News Articles in the Database

The SearchNewsDB class fetches news articles using the NewsAPI, processes the contents by splitting the text into chunks, and stores these in a Chroma vector database for later retrieval.
Tool 2: Retrieve News Articles from the Database

The GetNews class allows for the retrieval of relevant news articles based on a query, searching the previously stored news data in the Chroma database.
Tool 3: Search for News Articles on the Web

The DuckDuckGoSearchRun tool is used to search for news articles on the web, providing additional resources if needed.
Creating Agents and Tasks
News Search Agent: This agent is tasked with searching for news articles related to a specific topic (e.g., "AI 2024") and generating key points from the latest news.
Writer Agent: This agent verifies the topics received using the database and web search tools, and then writes detailed summaries based on the information retrieved.
Running the Script
To execute the script, simply run:

bash
Copy code
python app.py
Output
The script creates a "crew" consisting of the news search and writer agents, who work together to accomplish the task of generating key points and summaries for the given topics. The result of the execution is printed out, demonstrating the Retrieval-Augmented Generation (RAG) process in action.

Contributing
Contributions to this project are welcome. If you have suggestions for improvements or encounter any issues, please feel free to open a pull request or issue.

License
This project is licensed under the MIT License. See the LICENSE file for more details.
