# Chat Log Preparation for Semantic Search

This repository demonstrates the process of preparing chat-based data for semantic search. Semantic search allows you to find information not just based on keyword matching but by understanding the meaning and context of the text.

## Data

1. chat_data.db contains the raw chat log
2. memory_composite.db contains the processed chat data ready for search
3. chroma/ contains the vector db related objects

## Steps

1. **Transform Raw Chat Log into Sessions**: The first step involves transforming the raw chat log into a sequence of sessions. Sessions are logical divisions that help organize the conversation flow.

2. **Divide into Chunks with Overlap**: To efficiently process the chat data, it is divided into smaller chunks with some overlap. This ensures that important context is not lost.

3. **Add IDs Using MD5 and Timestamp**: Each chunk is assigned a unique identifier using a combination of MD5 hash and timestamp. This unique ID helps in tracking and retrieval.

4. **Add a Summary Using OpenAI**: OpenAI's language models are used to generate summaries for each chunk. These summaries provide a concise representation of the chunk's content.

5. **Create Embeddings for Summaries**: The generated summaries are converted into embeddings, which are numerical representations of text. These embeddings enable efficient semantic search.

6. **Save the Resulting Object into an SQLite Database**: The processed chat data, including chunks, IDs, summaries, and embeddings, is saved into an SQLite database. This organized storage facilitates quick retrieval and analysis.

7. **Instantiate and Populate a Chroma Vector DB Collection**: Chroma Vector DB is a database system that specializes in storing and querying embeddings. Here, an appropriate collection is instantiated and populated with the embeddings of the chat summaries.

8. **Query the Collection**: With the data prepared and stored, you can now perform semantic searches within the Chroma Vector DB collection. This allows you to find relevant information based on the meaning and context of the text, rather than just keywords.

By following these steps, you can efficiently prepare and utilize chat-based data for semantic search, opening up new possibilities for information retrieval and analysis.
