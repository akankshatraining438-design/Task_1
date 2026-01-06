1. Chunking Strategy -The system utilizes a Semantic-Recursive Splitting approach.Logic: Instead of cutting text at a fixed character count, it first attempts to split by double newlines (\n\n) to preserve paragraph integrity.
2. Embedding Choice - 
The system uses the all-MiniLM-L6-v2 model from the Sentence-Transformers library.
Reasoning: This is a widely respected Hugging Face model optimized for speed and efficiency.
3. Confidence Logic-
The confidence score is calculated using Manual Cosine Similarity via NumPy.Calculation: The score is derived by calculating the dot product of the query vector and the document vector, divided by the product of their magnitudes.
4. Hallucination Prevention-
Strict System Prompting: The LLM is instructed with a "System-Level" command: "Answer ONLY from the context provided. If the answer is not there, say I don't know."
5. Limitations -
API Dependency: The system relies on the Hugging Face Inference API. If the external API is down or the rate limit is reached, the system will fail to generate answers.
