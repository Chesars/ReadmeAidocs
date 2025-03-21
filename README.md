# InternetWhisper: Conversational AI Chatbot with Internet Access

## Project Overview
InternetWhisper is an advanced conversational AI chatbot inspired by platforms like You.com and Google's Bard. It combines the power of generative AI with real-time internet access to provide accurate and up-to-date information. The chatbot leverages Redis Vector DB for caching previously retrieved data, reducing redundant internet queries, and integrates Google's Custom Search API for web scraping.

## Features
- **Real-Time Internet Access**: Fetches live data from the web to answer user queries.
- **AI-Powered Conversations**: Uses OpenAI's GPT-3.5 Turbo for generating responses.
- **Caching with Redis Vector DB**: Stores and retrieves data efficiently to optimize performance.
- **Customizable Scraping**: Supports both local and remote scraping for flexible data retrieval.
- **Streamlit Frontend**: Provides an interactive user interface for seamless interaction.

## Technical Explanation
The project is built using a microservices architecture with the following components:
- **FastAPI Backend**: Handles API requests and integrates with OpenAI's GPT-3.5 Turbo.
- **Redis Vector DB**: Used for caching and retrieving vectorized data.
- **Google Custom Search API**: Fetches search results for user queries.
- **Playwright**: Enables advanced web scraping with JavaScript rendering.
- **LangChain Splitter**: Splits large text into manageable chunks for processing.
- **Streamlit Frontend**: Provides a user-friendly interface for interacting with the chatbot.

### Key Modules
1. **Retriever**: Combines search, scraping, and embeddings to retrieve relevant data.
2. **Splitter**: Processes and clusters text into meaningful chunks.
3. **Embeddings**: Generates vector representations of text using OpenAI embeddings.
4. **Scraper**: Fetches and parses web content, supporting both local and remote scraping.
5. **Cache**: Stores and retrieves vectorized data using Redis.

## Installation

### Prerequisites
- Docker and Docker Compose installed on your system.
- API keys for Google Custom Search and OpenAI.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/internetwhisper.git
   cd internetwhisper
   ```

2. Create a `.env` file:
   Copy the provided `.env.example` file and fill in the required API keys and configurations:
   ```bash
   cp .env.example .env
   ```

3. Build and run the application:
   ```bash
   docker-compose build
   docker-compose up
   ```

4. Access the application:
   - Frontend: [http://localhost:8501](http://localhost:8501)
   - Backend API: [http://localhost:8000/docs](http://localhost:8000/docs)

## Usage

### Interacting with the Chatbot
1. Open the Streamlit frontend in your browser.
2. Enter your query in the chat input box.
3. The chatbot will fetch relevant data from the internet, process it, and respond in real-time.

### Switching Scrapers
- **Local Scraper**: Default option for basic web scraping.
- **Remote Scraper**: For advanced JavaScript-rendered pages. Update `main.py` to use `ScraperRemote`.

### OpenAPI Documentation
The backend provides OpenAPI documentation for all available endpoints. Access it at [http://localhost:8000/docs](http://localhost:8000/docs).

## Environment Variables
The following variables must be configured in the `.env` file:
- `GOOGLE_API_HOST`: Base URL for Google Custom Search API.
- `GOOGLE_API_KEY`: Your Google API key.
- `GOOGLE_CX`: Custom search engine ID.
- `OPENAI_API_KEY`: Your OpenAI API key.
- `HEADER_ACCEPT_ENCODING`: Set to `gzip`.
- `HEADER_USER_AGENT`: User agent string for web scraping.

## Contributing
We welcome contributions! To contribute:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to your branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a pull request.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact
For questions or feedback, please contact [santiagomorillosegovia@gmail.com](mailto:santiagomorillosegovia@gmail.com).
