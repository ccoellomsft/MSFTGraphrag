![image](https://github.com/user-attachments/assets/d6bcfcd0-a1af-4d00-a47c-405f24a6ea0b)


# Microsoft GraphRAG:
- Works using Python 3.10
- GraphRah Version = 2.3.0

## Overview


GraphRAG is a structured, hierarchical approach to Retrieval Augmented Generation (RAG), as opposed to naive semantic-search approaches using plain text snippets. The GraphRAG process involves extracting a knowledge graph out of raw text, building a community hierarchy, generating summaries for these communities, and then leveraging these structures when perform RAG-based tasks.

To learn more about GraphRAG and how it can be used to enhance your language model's ability to reason about your private data, please visit the Microsoft Research Blog Post.

## Query Engine


The Query Engine is the retrieval module of the Graph RAG Library. It is one of the two main components of the Graph RAG library, the other being the Indexing Pipeline (see Indexing Pipeline). It is responsible for the following tasks:

Local Search
Global Search
DRIFT Search
Question Generation

## Local Search

Local search method generates answers by combining relevant data from the AI-extracted knowledge-graph with text chunks of the raw documents. This method is suitable for questions that require an understanding of specific entities mentioned in the documents (e.g. What are the healing properties of chamomile?).

## Global Search

Global search method generates answers by searching over all AI-generated community reports in a map-reduce fashion. This is a resource-intensive method, but often gives good responses for questions that require an understanding of the dataset as a whole (e.g. What are the most significant values of the herbs mentioned in this notebook?).


## Drift Search
DRIFT Search introduces a new approach to local search queries by including community information in the search process. This greatly expands the breadth of the query’s starting point and leads to retrieval and usage of a far higher variety of facts in the final answer. This addition expands the GraphRAG query engine by providing a more comprehensive option for local search, which uses community insights to refine a query into detailed follow-up questions.

## Basic Search
GraphRAG includes a rudimentary implementation of basic vector RAG to make it easy to compare different search results based on the type of question you are asking. You can specify the top k txt unit chunks to include in the summarization context.


## Conclusion

Microsoft GraphRAG represents a significant step forward in retrieval-augmented generation, particularly for tasks requiring a global understanding of datasets. By incorporating knowledge graphs, it offers improved performance, making it ideal for complex information retrieval and analysis.

For those experienced with basic RAG systems, GraphRAG offers an opportunity to explore more sophisticated solutions, although it may not be necessary for all use cases.
Retrieval Augmented Generation (RAG) is often performed by chunking long texts, creating a text embedding for each chunk, and retrieving chunks for including in the LLM generation context based on a similarity search against the query. This approach works well in many scenarios, and at compelling speed and cost trade-offs, but doesn't always cope well in scenarios where a detailed understanding of the text is required.

GraphRag ( [microsoft.github.io/graphrag](https://microsoft.github.io/graphrag/) )
