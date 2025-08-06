## ClauseCraft

**Project Idea: AI-Powered Legal Document Analyzer**

This project is a complete pipeline for automated legal document analysis using advanced AI techniques. It leverages large language models (LLMs) with Retrieval-Augmented Generation (RAG), structured output formatting, API function calling, system/user prompts, and tunable parameters.

**Project Overview**

- **Objective:** Automate extraction, summarization, and validation of key info (e.g., parties, dates, amounts, clauses) from legal contracts and documents.
- **Users:** Legal professionals and compliance teams.

**Features Covering Required Topics**

1. **System Prompt and User Prompt**
   - System prompt defines overall assistant behavior: "You are a legal assistant. Always provide structured summaries of uploaded contracts and clearly distinguish between factual extraction and opinion."
   - User prompt collects queries: "Summarize the main obligations for Party A in this contract." or "Extract all payment terms from this document."

2. **Tuning Parameters**
   - Allow users to change model parameters such as:
     - Temperature (for response creativity vs. precision)
     - Output verbosity level (short/medium/detailed summaries)
     - RAG retrieval count (number of document chunks retrieved per query)

3. **Structured Output**
   - Return information in clear, machine-readable formats:
   - Or generate rich, structured Markdown tables for legal review.

4. **Function Calling**
   - Use LLM function-calling abilities to:
     - Fetch specific data (e.g., party contact details via API)
     - Validate clauses via external compliance/legislation APIs
     - Schedule reminders for key contract dates

5. **RAG (Retrieval-Augmented Generation)**
   - Store all uploaded contracts in a vector database (e.g., Chroma, Pinecone)
   - When a question is asked, first retrieve the most semantically relevant chunks using vector search, then pass along with the user/system prompts to the LLM for improved contextualized answers.

**Workflow Example**

1. User uploads contract PDF.
2. System extracts and embeds content into vector database.
3. User asks: “List all termination clauses and explain triggers.”
4. Pipeline:
   - System prompt sets role/context.
   - User prompt specifies task.
   - RAG retrieves relevant text passages.
   - LLM processes retrieved context, extracting and structuring info into a JSON table.
   - If needed, model calls compliance API to check if triggers violate local law.
   - User receives JSON/Markdown output and has options to tweak verbosity or API checks.

   

This project demonstrates modern applied AI with a strong mix of prompt engineering, LLM features, RAG, API integration, and user-centric configuration, making it ideal for exploration and practical deployment.