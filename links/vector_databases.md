## pgvector

Links

[PostgreSQL and Pgvector: Now Faster Than Pinecone, 75% Cheaper, and 100% Open Source](https://www.timescale.com/blog/pgvector-is-now-as-fast-as-pinecone-at-75-less-cost/)

### Examples

The following links and repo is a nice starting point if you want to use the PostgreSQL database as a Vector database.

##### Smarter Postgres LLM with Retrieval Augmented Generation

The blog post “Smarter Postgres LLM with Retrieval Augmented Generation” by Paul Ramsey, published on December 9, 2024, discusses enhancing Large Language Models (LLMs) using Retrieval Augmented Generation (RAG) within PostgreSQL. RAG improves LLM accuracy by integrating external data sources, enabling models to provide precise answers in specific domains. The article demonstrates this by creating a query function to answer questions about “Star Trek: The Next Generation” episodes. It involves building a database of episode plot summaries, generating embeddings with the pgvector extension, and utilizing these embeddings to retrieve relevant information, thereby reducing LLM hallucinations and enhancing response accuracy.

[Link](https://www.crunchydata.com/blog/smarter-postgres-llm-with-retrieval-augmented-generation)

##### Accessing Large Language Models from PostgreSQL

The blog post “Accessing Large Language Models from PostgreSQL” by Paul Ramsey, published on November 13, 2024, introduces a PostgreSQL extension that facilitates interaction with Large Language Models (LLMs) directly from the database. This extension provides three primary functions:

• openai.models(): Retrieves a list of available models from the API.
• openai.prompt(context text, prompt text): Returns a text response generated by the model based on the provided context and prompt.
• openai.vector(prompt text): Generates a vector embedding for the given prompt text.

The extension is compatible with both cloud-hosted services like OpenAI and locally hosted models such as Ollama, utilizing the OpenAI API standard for communication. By setting appropriate session variables (openai.api_key, openai.api_uri, openai.prompt_model, and openai.embedding_model), users can configure the extension to interact with their chosen LLM service.

An example application demonstrated in the article is sentiment analysis. By creating a feedback table and implementing a trigger function that calls openai.prompt(), the system can automatically classify the sentiment of customer feedback upon insertion or update. This integration showcases how LLMs can be leveraged within PostgreSQL to enhance data processing capabilities.

[Link](https://www.crunchydata.com/blog/accessing-large-language-models-from-postgresql)

##### Repo: OpenAI API Client for PostgreSQL

The GitHub repository pgsql-openai provides PostgreSQL helper functions to interact with the OpenAI API. Leveraging the http extension for web access, it enables functionalities such as:
• Classification and Text Analysis: Automate the analysis and categorization of freeform text fields, like reviews and comments, by integrating AI triggers within the database.
• Similarity Searching: In combination with the pgvector extension, identify the “N most similar” items in a dataset, facilitating recommendation engines to find related items based on user interest.
• Retrieval-Augmented Generation (RAG): Enhance natural language AI queries by incorporating relevant contextual documents, improving the accuracy and relevance of AI-generated responses.

The extension offers key functions:
• **openai.models()**: Retrieves a list of available AI models via the API.
• **openai.prompt(context text, query text, [model text])**: Generates a text response from the model based on the provided context and query.
• **openai.vector(query text, [model text])**: Produces a JSON-formatted float array embedding for the given query, suitable for use with the pgvector extension.

Configuration involves setting session keys for the API URI, API key, prompt model, and embedding model. The extension supports both cloud-hosted services like OpenAI and locally hosted models such as Ollama, utilizing the OpenAI API standard for communication.

[Link](https://github.com/pramsey/pgsql-openai/tree/main)



## sqlite-vec

[sqlite-vec](https://alexgarcia.xyz/sqlite-vec/installation.html) is an extension for **SQLite** that introduces vector 
operations and similarity searches, enhancing SQLite’s capabilities for handling vector data.
