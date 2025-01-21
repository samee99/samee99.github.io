**An AI agent engineer**

*January 2025*

The possibility of creating production-grade AI agentic workflows increases with the release of each new reasoning model along with improvements in the models’ ability to call tools. Work traditionally performed by humans can now start to get offloaded to these AI agents. 

In this sense, the Software 2.0 era, where the computer effectively writes the code and executes the task is closing in. This also means that the Software as a Service era, where the software assisted the human agent, will slowly get augmented and replaced by the Service as Software era. In the Service as Software era, the AI agent(s), with access to tools, will try to achieve a high-level, abstract goal traditionally left to humans. This represents a major disruption in how humans have viewed their relationship with computers. AI agents with access to capital can allocate resources to hire human labor or to rent compute (e.g. GPUs) to execute tasks. 

Many roles traditionally held by humans in corporations will undergo disruption. Well-defined roles such as Sales Development Representative or Customer Support are already experiencing change. But in this write-up, I want to focus on the AI/ML engineer. What could be more disruptive than the AI agent acting as an AI/ML engineer, creating a virtuous feedback loop where the agent continuously improves its own capabilities? 

How can we build an AI/ML engineer? Let’s call him Neo. One method is to identify all the tasks that an AI engineer performs and try to build a system that can automate them. Another approach might be to take one specific task, typically performed by an AI engineer, automate it, and then gradually broaden Neo's capabilities. We will use the second approach as it provides a more constrained scope and allows an easier angle of attack. 

Let’s assume that Neo's initial competency is building a Retrieval Augmented Generation (RAG) system. What is the typical workflow used by engineers to build RAG systems? While creating a demo for RAG is straightforward—using a fixed large language model (LLM), embedding model, and other hyperparameters such as top-k, reranker, and chunk size—developing a production-grade RAG system involves a more intricate process. It requires searching through a wide range of hyperparameters (including parsers, LLMs, embedding models, etc.) and evaluating each combination to identify the optimal configuration.

Although searching for optimal hyperparameters is a compute-intensive task, it is a well-defined problem that Neo can systematically navigate. To achieve this, Neo needs to integrate an AutoML process that iterates through various options for retrieval and generation tools. Additionally, Neo requires an assistant LLM to evaluate and judge each configuration option.

Assuming that such an AutoML system is accessible as a tool, Neo must begin by collecting specific RAG requirements from the user. This can be performed via a chat interface where the user provides Neo information about their project scope and Neo asks clarifying questions to correctly interpret their needs. Beyond accessing the necessary data, Neo ensures that the user provides "Golden Questions & Answers"—a set of high-quality queries and responses that Neo uses to evaluate and determine the optimal hyperparameters given cost, latency, and accuracy constraints. 

Neo formalizes the requirements by delivering a comprehensive requirements document for the user's review and approval. Based on this document, Neo proposes an architecture for the RAG system and provides a detailed project breakdown with defined milestones. The proposed system design undergoes another review cycle with the user to ensure alignment. Upon formal approval of the system design, Neo proceeds to build the agreed-upon architecture and utilizes the AutoML system to identify the optimal hyperparameters for the RAG system.

Neo deploys the optimal configuration for the user, conducts thorough testing, and delivers the validated codebase along with comprehensive documentation. This phase also includes security and compliance checks to ensure the system meets all necessary standards. Subsequently, Neo implements system monitoring to maintain uptime and performance.

To gather user feedback, Neo employs mechanisms such as simple approval ratings or comparative evaluations, where users select the better response from presented options. Additionally, Neo tracks user interaction touchpoints to assess the user's proficiency level. This ensures that the provided documentation is both readable and tailored to the user's competency.

Neo leverages AutoML capabilities to optimize both the retriever and generation tools within a RAG system. To expand its utility across a wider range of use cases, Neo must continually identify and integrate additional tools, developing mechanisms to optimize each as needed.

For example, consider a warehouse manager who requests Neo to develop a system that counts the number of humans in a video stream and sends an email alert if more than ten humans are detected. In this scenario, Neo would need to gather specific requirements, such as determining the number of video frames to analyze and assessing the system's associated costs. Subsequently, Neo would apply the most effective object detection model available to accurately count the number of humans, ensuring the system operates efficiently and meets the manager's needs.

This process would require a search through all possible object detection models along with optimization of the hyperparameters as well as any preprocessing the video frames may require to achieve the result. 
*Take me [home](https://sameeurrehman.com/)* 
