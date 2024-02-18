# dikaioqa

Retrieval Augmented Generation on domain specific legal dataset

Process:
1. Create Vectorstore for our data
   Preprocess texts for efficient embedding: remove accents convert to lowercase
   Tokenize texts based on openai tokenizer (estimation of i/o capabilities)
   Accordingly split data into chunks with overlap
   Embedd chunks using ada 002
   Store in Faiss vectorstore
2. Create a user querry and retriever
   Based on the same embedding the querry is used in conjuction with the retriever
   to perform a similarity search on the vectorstore (Euclidian distance-based)
   Select and filter most relevant texts (trial and error)
3. Create a prompt and feed context chunks along with the querry to a Gpt-4 based question-answering chain
4. Also try contextual compression retrieval on fetched docs
5. Compare results     
