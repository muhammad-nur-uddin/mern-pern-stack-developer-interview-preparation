# 🎯 LangChain Fundamentals

## Q01. What is LangChain, and why do we use it?

Interview-ready Answer — বাংলা

LangChain হলো একটি open-source framework, যা ব্যবহার করে Large Language Model বা LLM-ভিত্তিক application তৈরি করা যায়। এটি prompt templates, model integrations, output parsers, retrievers এবং tools-এর মতো বিভিন্ন component একসঙ্গে connect করতে সাহায্য করে।
আমরা LangChain ব্যবহার করি কারণ বাস্তব AI application-এ শুধু LLM call করাই যথেষ্ট নয়। অনেক সময় external data retrieve করা, conversation history maintain করা এবং একাধিক processing step execute করার প্রয়োজন হয়। LangChain এসব কাজের জন্য reusable abstractions এবং integrations প্রদান করে। উদাহরণস্বরূপ, এটি ব্যবহার করে PDF documents থেকে relevant information retrieve করে উত্তর দেওয়ার মতো RAG application তৈরি করা যায়।

Interview-ready Answer — English

LangChain is an open-source framework for building applications powered by Large Language Models, or LLMs. It provides components and integrations for working with prompts, language models, output parsers, retrievers, and tools.
We use LangChain because real-world AI applications often need more than a simple LLM API call. They may need to retrieve information from external data sources, maintain conversation history, or connect multiple processing steps. LangChain provides reusable abstractions to build these workflows. For example, we can use it to build a RAG application that retrieves relevant information from PDF documents and uses that information to answer user questions.

## Q02. What is the difference between an LLM and LangChain?

Interview-ready Answer — বাংলা

LLM এবং LangChain-এর মধ্যে প্রধান পার্থক্য হলো, LLM একটি AI model, আর LangChain একটি framework।
LLM user-এর input-এর ভিত্তিতে text generate করতে পারে। উদাহরণস্বরূপ, GPT, Claude এবং Gemini হলো LLM-এর উদাহরণ।
অন্যদিকে, LangChain ব্যবহার করে আমরা LLM-কে prompt templates, external data sources, retrievers এবং tools-এর সঙ্গে connect করতে পারি। এটি একাধিক processing step-কে একটি workflow-তে সাজাতেও সাহায্য করে।
উদাহরণস্বরূপ, একটি RAG application-এ LangChain relevant documents retrieve করে সেগুলো LLM-এর কাছে পাঠানোর workflow তৈরি করতে সাহায্য করতে পারে। LLM সেই context ব্যবহার করে উত্তর generate করে। অর্থাৎ, LLM উত্তর তৈরি করে, আর LangChain সেই LLM-কে ব্যবহার করে application তৈরি করতে সাহায্য করে।

Interview-ready Answer — English

The main difference between an LLM and LangChain is that an LLM is an AI model, while LangChain is a framework for building LLM-powered applications.
An LLM can understand input and generate text based on that input and its training. Examples include GPT, Claude, and Gemini.
LangChain helps us connect an LLM with other components, such as prompt templates, external data sources, retrievers, and tools. It also helps us organize multiple processing steps into a workflow.
For example, in a RAG application, LangChain can help retrieve relevant documents and pass their content to an LLM. The LLM then uses that context to generate an answer. In simple terms, the LLM generates the response, while LangChain helps us build the application around it.

## Q03. What are the main components of LangChain?

Interview-ready Answer — বাংলা

LangChain-এর প্রধান components হলো Models, Prompts, Output Parsers, Runnables, Document Loaders, Text Splitters, Embeddings, Vector Stores, Retrievers, Tools, Agents এবং Chat History management।

Models LLM-এর সঙ্গে interact করতে সাহায্য করে। Prompts model-এর জন্য input ও instructions তৈরি করে। Output Parsers response-কে প্রয়োজনীয় format-এ রূপান্তর করে, আর Runnables একাধিক processing step connect করতে সাহায্য করে।

Document Loaders ও Text Splitters external documents process করে। Embeddings এবং Vector Stores semantic search-এর জন্য ব্যবহৃত হয়। Retrievers relevant information খুঁজে বের করে। Tools এবং Agents model-কে external actions সম্পাদন করতে সাহায্য করে। Chat History management conversation-এর আগের messages সংরক্ষণ ও ব্যবহার করতে সাহায্য করে।

এই components প্রয়োজন অনুযায়ী একসঙ্গে ব্যবহার করে আমরা chatbot, RAG system এবং tool-using AI application তৈরি করতে পারি।

Interview-ready Answer — English

The main components of LangChain include Models, Prompts, Output Parsers, Runnables, Document Loaders, Text Splitters, Embeddings, Vector Stores, Retrievers, Tools, Agents, and Chat History management.

Models help us interact with language models. Prompts define the instructions and input for a model. Output Parsers help convert model responses into the required format. Runnables allow us to connect multiple processing steps into a workflow.

Document Loaders and Text Splitters help process external documents. Embeddings and Vector Stores support semantic search. Retrievers find relevant information based on a query. Tools allow an application to perform specific actions, while Agents can decide which tools to use based on the task. Chat History management helps preserve and reuse previous messages in a conversation.

We combine these components based on our requirements to build applications such as chatbots, RAG systems, and AI applications that use external tools.

## Q04. What is a Prompt Template in LangChain, and why is it useful?

## Q05. What is an Output Parser in LangChain, and how does it work?

# 🎯 Category 2: Models, Prompts & Messages

## Q06. What is the difference between a Chat Model and a traditional LLM?

## Q07. How do you integrate an LLM provider, such as OpenAI or Groq, with LangChain?

## Q08. What are System, Human, and AI messages in LangChain?

## Q09. What is the difference between `invoke()`, `stream()`, and `batch()`?

## Q10. How do you get structured JSON output from an LLM using LangChain?

# 🎯 Category 3: Chains & LCEL

## Q11. What is a Chain in LangChain?

## Q12. What is LCEL (LangChain Expression Language)?

## Q13. What does the pipe (`|`) operator do in LCEL?

## Q14. What is `RunnablePassthrough`, and when would you use it?

## Q15. What is the difference between sequential execution and parallel execution in LangChain?

# 🎯 Category 4: Memory & Chat History

## Q16. How can you maintain conversation history in a LangChain application?

## Q17. What is the role of `MessagesPlaceholder` in a chat prompt?

## Q18. What is the difference between short-term chat history and long-term memory?

## Q19. How would you build a chatbot that remembers previous messages across multiple requests?

# 🎯 Category 5: Embeddings, Vector Stores & RAG

## Q20. What are embeddings, and why are they used in LangChain?

## Q21. What is a Vector Store, and how does it work?

## Q22. What is RAG (Retrieval-Augmented Generation), and why is it useful?

## Q23. What is a Retriever in LangChain, and how is it different from a Vector Store?

## Q24. What is a Document in LangChain, and what are `page_content` and `metadata`?

## Q25. What is a Text Splitter in LangChain, and why do we split documents into chunks?

# 🎯 Category 6: Tools, Agents & Practical Applications

## Q26. What are Tools in LangChain, and how do you create a custom tool?

## Q27. What is an Agent in LangChain, and how is it different from a Chain?

## Q28. What is Tool Calling, and how does an LLM decide when to call a tool?

## Q29. What is an Agent Executor, and how does an agent execute multiple steps?

## Q30. How would you build a simple RAG-based question-answering application using LangChain?
