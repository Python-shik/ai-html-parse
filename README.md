# AI-Powered HTML Parser

## Installation

### Prerequisites

- Python 3.8 or higher
- Required Libraries:
  - `requests`
  - `bs4` (BeautifulSoup)

### Steps

Clone the repository:
   ```bash
   git clone https://github.com/pythonshik/ai-html-parser.git
   ```

OR


Install with pip:
   ```bash
   pip install ai-html-parse
   ```

---

## Usage

### Example

1. Import the `AIparser` class:
   ```python
   from AIparse import AIparser
   ```
2. Initialize the parser with a URL:
   ```python
   element = AIparser("https://www.youtube.com/@PythonShik")
   ```
3. Parse specific elements:
   ```python
   for i in ["number of videos", "number of subscribers"]:
       parsed_data = element.parse(i)
       print(f"{parsed_data['explain']}: {parsed_data['value']}")
   ```
4. Output example:
   ```json
   {
     "value": "96",
     "explain": "Number of subscribers",
     "result": "96 subscribers"
   }
   ```

---

## Overview

This project is an AI-powered HTML parser designed to extract specific data from web pages using Google Gemini's text generation API. The parser processes the HTML source code of a webpage, identifies specific elements, and returns the desired information in a structured JSON format.

### Key Features

- **AI Integration**: Utilizes Google Gemini for intelligent text analysis.
- **HTML Parsing**: Extracts and processes HTML elements using BeautifulSoup.
- **Customizable Instructions**: Supports user-defined parsing instructions.
- **JSON Output**: Provides clear and structured results in JSON format.

---

## How It Works

1. **User Input**: Provide a URL and the target element to parse.
2. **HTML Fetching**: The tool fetches the HTML source code of the webpage.
3. **AI Analysis**: The HTML source and target element are sent to the AI for processing.
4. **JSON Output**: The AI generates a structured response containing the extracted information.

---

## File Descriptions

### 1. `BASE.py`

The core class for interacting with Google Gemini's text generation API.

- **Features**:
  - API key management.
  - Methods for adding and managing conversation history.
  - Text generation using the `generate()` method.
- **Key Methods**:
  - `history_add(role, content)`: Adds messages to the conversation history.
  - `generate()`: Sends data to gemini API and retrieves the generated text.
  - `export_history(filename)`: Saves conversation history to a file.
  - `import_history(filename)`: Loads conversation history from a file.
  - `clear_history(filename)`: Clears the conversation history.

### 2. `prompts.py`

Defines the instruction format for AI tasks.

- **Key Class**: `Instructions`
  - `first_instruction`: Provides a detailed guide for parsing HTML elements and formatting the response.

### 3. `main.py`

The main entry point for the application.

- **Features**:
  - Manages the parsing process using `AIparser`.
  - Configures and interacts with the `Gen` class for AI communication.
  - Outputs results for specific elements like "number of subscribers" or "number of videos".
- **Key Methods**:
  - `AIparser.__init__`: Initializes the parser with a URL and target element.
  - `AIparser.parse(element)`: Parses the given element and retrieves AI-generated results.

---

## Target Audience

This tool is ideal for:

- **Marketers and Analysts**: For monitoring trends, gathering competitor data, and extracting insights.
- **Small and Medium Businesses**: To automate tasks like market monitoring or customer review aggregation.
- **SEO Specialists**: To analyze site content, keywords, and metadata.
- **Developers and Freelancers**: To speed up the execution of client parsing tasks.
- **Journalists and Bloggers**: To gather data for articles and posts effortlessly.

---

## Limitations

- **Speed**: Processing time can take up to 45 seconds due to the AI generation.
- **Dependencies**: Requires an active internet connection and a valid API key.
- **Scalability**: Not optimized for high-frequency requests.

---

## Potential Use Cases

- Monitoring changes on web pages.
- Extracting market research data.
- Analyzing competitors' content.
- Automating reporting tasks.

---

## Future Improvements

- Optimize performance with batch processing and caching.
- Add support for local AI models to reduce dependency on external APIs.
- Expand parsing capabilities to include other data formats like JSON and XML.
- Develop a user-friendly interface (e.g., Telegram bot or web app).

---

## Contributing

Feel free to contribute to the project by submitting issues or pull requests.

---

## License

This project is licensed under the MIT License.
