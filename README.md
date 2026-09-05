# Local LLM Website Summarizer

A simple Python project that summarizes website content using a locally running Large Language Model through Ollama.

## Overview

The project takes a website URL, fetches the webpage, extracts the useful text using BeautifulSoup, and sends the extracted content to a local LLM for summarization. The generated summary is then displayed as formatted Markdown inside the Jupyter Notebook.

## How It Works

Website URL → Requests → BeautifulSoup → Clean Website Text → Prompt → Ollama + Llama 3.2 1B → Summary → Markdown Display

## Features

- Scrapes website content from a given URL
- Removes unnecessary HTML elements such as scripts, styles, images, and inputs
- Uses a local LLM through Ollama
- Generates short summaries in Markdown
- Does not require an external LLM API key

## Tech Stack

- Python
- Requests
- BeautifulSoup
- Ollama
- Llama 3.2 1B
- Jupyter Notebook

## Running the Project

Create and activate a virtual environment:

    python -m venv .venv

On Windows:

    .venv\Scripts\activate

Install the required packages:

    pip install -r requirements.txt

Make sure Ollama is installed and the model is available:

    ollama pull llama3.2:1b

Then open `Website_summarizer.ipynb` in Jupyter and run the notebook cells.

Example:

    display_summary("https://www.nasa.gov")

## Limitations

Some websites may block automated requests, while websites that rely heavily on JavaScript may not be scraped correctly. Very large webpages can also provide more text than a small local model can handle effectively.

## Future Improvements

- Better webpage content extraction
- Handling long webpages through text chunking
- Error handling for blocked or unavailable websites
- Streamlit interface
- Support for multiple URLs
- Support for different local models