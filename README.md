# Ai-Agent
 --------{Project Description}
This AI Agent project is designed to automate the process of gathering and processing web data. The user uploads a CSV file containing a list of entities (e.g., company names) and specifies a custom search query for each entity. The AI agent performs a web search using the provided query and retrieves the relevant data, which is then processed using a language model (LLM) to extract structured information (e.g., emails, addresses, etc.).

----------{The project allows users to}:

Upload a CSV file with entities.
Define custom prompts for web searches.
Retrieve, parse, and extract information.
View the results in a structured format.
Download the extracted data as a CSV file.
----------{Setup Instructions}
To set up and run the application, follow these steps:

1. Clone the Repository
Clone the repository to your local machine using the following command:

bash
Copy code
git clone https://github.com/yourusername/AI-Agent.git
2. Install Dependencies
Navigate to the project directory and install the necessary Python dependencies:

bash
Copy code
cd AI-Agent
pip install -r requirements.txt
3. Run the Streamlit App
Once the dependencies are installed, you can run the application with:

bash
Copy code
streamlit run app.py
This will start a local server, and you can open the application in your browser by navigating to http://localhost:8501.

Usage Guide
Uploading a CSV File
Click on the "Browse" button in the dashboard to upload a CSV file that contains a list of entities (e.g., company names).
The CSV should have one column with the names of the entities you want to search for (e.g., companies, products).
Defining Search Queries
In the Search Query Input Box, you can enter a custom query. For example:
"Get the email address of {company}"
"Find the phone number of {company}"
The placeholder {company} will be replaced dynamically with each entity from your CSV file.
Retrieving Data
Click on the "Run" button to initiate the web searches.
The AI agent will perform the search for each entity and extract the relevant information.
Once completed, the extracted data will be displayed in a table format within the dashboard.
Downloading Results
After the data is processed, you can download the extracted information as a CSV file using the "Download CSV" button.
The downloaded file will contain the entities and their corresponding extracted data.
--------------{API Keys and Environment Variables}
Required APIs:
SerpAPI (or other search APIs): To perform web searches and retrieve the search results.

Sign up for an API key at SerpAPI or another search API provider.

Add the API key to your environment variables as follows:

bash
Copy code
export SERPAPI_API_KEY='your_serpapi_key_here'
LLM API (Groq/OpenAI): For processing the web results and extracting structured information.

You can use the OpenAI GPT API or Groq for this purpose.

Create an account and get your API key from OpenAI or Groq.

Add the LLM API key to your environment variables:

bash
Copy code
export LLM_API_KEY='your_llm_api_key_here'
Storing Keys Securely
Make sure to store your API keys and other sensitive information in a .env file or in your environment variables to keep them secure. You can use a package like python-dotenv to load these environment variables from a .env file automatically.

Create a .env file in the root directory of your project and add the following:

plaintext
Copy code
SERPAPI_API_KEY=your_serpapi_key_here
LLM_API_KEY=your_llm_api_key_here
Then, use the dotenv package to load the variables in your app.py:

python
Copy code
from dotenv import load_dotenv
import os

load_dotenv()

SERPAPI_API_KEY = os.getenv('SERPAPI_API_KEY')
LLM_API_KEY = os.getenv('LLM_API_KEY')
--------------{Optional Features}
1. Advanced Query Templates
Users can now enter more complex search queries, such as:
"Get the email and phone number for {company}".
The query will process both fields in a single request.
2. Google Sheets Integration (Optional)
If you prefer, you can integrate Google Sheets to input data instead of CSV. Instructions to link Google Sheets will be added upon request.
3. Error Handling
Robust error-handling mechanisms are included to ensure smooth execution. The system will retry failed queries and notify users in case of issues.
