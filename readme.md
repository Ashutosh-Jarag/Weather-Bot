# Weather Bot

Weather Data Agent Project


Overview

This project implements a weather data agent using Python, LangChain, and external APIs to fetch and process weather information and travel-related queries. The agent can answer questions about weather conditions in specific locations and provide travel information, such as ways to travel between cities.
Features

Weather Data Retrieval: Fetches current weather data for a specified city using the Weatherstack API.
Travel Information: Provides travel options (e.g., bus, car, flight) between cities using DuckDuckGo search.
Conversational Agent: Utilizes LangChain's ReAct agent to process natural language queries and interact with tools.

Prerequisites
To run this project, you need the following:

Python 3.12 or higher
A valid Weatherstack API key (replace your_api_key in the code with your actual key)
A valid Google API key for the Gemini model (set in the environment variable GOOGLE_API_KEY)
Internet connection for API calls and search functionality

Installation

Clone or download the project repository.
Create a virtual environment (optional but recommended):python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate


Install the required Python packages:pip install langchain-openai langchain-community langchain-core requests duckduckgo-search



Setup

Set Environment Variables:

Set your Google API key:import os
os.environ["GOOGLE_API_KEY"] = "your_google_api_key"


Replace your_api_key in the get_weather_data function with your Weatherstack API key:url = f'https://api.weatherstack.com/current?access_key=your_weatherstack_api_key&query={city}'




Jupyter Notebook:

Ensure you have Jupyter installed (pip install jupyter).
Run the notebook weatherdata-agent.ipynb using:jupyter notebook weatherdata-agent.ipynb





Usage

Open the weatherdata-agent.ipynb notebook in Jupyter.
Execute the cells in sequence to:
Install dependencies.
Initialize the LangChain agent with the Gemini model and DuckDuckGo search tool.
Define the weather data tool using the Weatherstack API.
Run example queries, such as:
"3 ways to reach Goa from Kolhapur"
"Where is Kolhapur and what is the weather like there?"




The agent will process the queries and return responses based on search results or API data.

Example Queries

Travel Query: "3 ways to reach Goa from Kolhapur"
Output: Provides options like bus (4-6 hours), car (8-9 hours, ~450 km), and flight (quick but includes airport logistics).


Weather Query: "Where is Kolhapur and what is the weather like there?"
Output: Identifies Kolhapur's location (Maharashtra, India) and provides current weather (e.g., cloudy, 24°C to 31°C).



Project Structure

weatherdata-agent.ipynb: The main Jupyter notebook containing the project code.
Tools:
get_weather_data: A custom tool to fetch weather data via the Weatherstack API.
DuckDuckGoSearchRun: A LangChain tool for web searches.


Dependencies:
langchain-openai, langchain-community, langchain-core: For agent and tool integration.
requests: For making API calls.
duckduckgo-search: For web search functionality.



Notes

The get_weather_data tool is defined but not used in the provided agent setup, as the example queries rely on the DuckDuckGo search tool. To use the weather tool, add it to the tools list in the AgentExecutor setup:tools = [search_tool, get_weather_data]


The project uses the Gemini-1.5-Pro model from Google. Ensure your API key is valid and has access to this model.
The Weatherstack API requires a valid key. Sign up at Weatherstack to obtain one.
The notebook includes a warning about missing ipywidgets. To resolve this, run:pip install ipywidgets



Troubleshooting

API Key Issues: Ensure the Google and Weatherstack API keys are correctly set.
Dependency Errors: Verify all required packages are installed.
Search Tool Limitations: DuckDuckGo search results may vary based on network conditions or query specificity.

License
This project is for educational purposes and does not include a specific license. Ensure compliance with the terms of use for Weatherstack and Google APIs.
