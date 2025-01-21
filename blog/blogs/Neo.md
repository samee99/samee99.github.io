**An AI agent engineer**

*January 2025*

The possibility of creating production-grade AI agentic workflows increases with the release of each new reasoning model along with improvements in the models’ ability to call tools. Work traditionally performed by humans can now start to get offloaded to these AI agents. 

In this sense, the Software 2.0 era, where the computer effectively writes the code and executes the task is closing in. This also means that the Software as a Service era, where the software assisted the human agent, will slowly get augmented and replaced by the Service as Software era. In the Service as Software era, the AI agent(s), with access to tools, will look to achieve a high-level, abstract goal traditionally left to humans. This represents a major disruption in how humans have viewed their relationship with computers. AI agents with access to capital can now redirect capital to get human labor or to rent compute (e.g. GPUs) to help them execute tasks. 

Many roles traditionally held by humans in corporations will undergo disruption. Well-defined roles such as Sales Development Representative or Customer Support are already undergoing a nonlinear change. But in this write-up, I want to focus on the AI/ML engineer. What could be more disruptive than the AI agent acting as an AI/ML engineer, resulting in a virtuous feedback loop where the agent improves its own capability? 

How could one go about building an AI/ML engineer? Let’s call him Neo.

How could one go about building our AI engineer, Neo? One method would be to look at all possible tasks that an AI engineer performs and try to build a system that can automate them. Another approach might be to take one specific task, typically performed by an AI engineer, automate it, and then broaden the circle of competence to handle more tasks. The second approach is better constrained and allows an easier angle of attack so we will try using it. 

Let’s assume that the first task that the agent has competence in is the ability to build a Retrieval Augmented Generation system. What is the typical workflow use by engineers to build RAG? As I wrote in the previous blog, it’s easy to build a demo for RAG where we use a fixed LLM, embedding model and other hyperparameters (e.g. top-k, reranker, chunk size). However, in addition to figuring out the RAG architecture, building a production-grade RAG system requires searching across all possible hyperparameters (parsers, LLM, embedding models, etc.) and evaluating each option to find the optimal configuration. 

Search is a compute intensive task, but it is a clearly defined problem that Neo can traverse. Neo needs to build or have access to an AutoML process that cycles through the different options for the optimal retrieval and generation tool, and an assistant LLM that acts as a judge to evaluate each option. 

Assuming that such an AutoML system exists as a tool call, Neo has to start with collecting requirements from the user on their specific RAG requirements. This can be performed via a chat interface where the user provides Neo information about their project scope and Neo asks clarifying questions to correctly interpret the needs of the user. In addition to getting access to the data, Neo always makes sure to request the user to share Golden Questions & Answers that Neo will use to evaluate and identify the optimal hyperparameters. 

Neo then has a formal handshake with the user on the requirements by delivering a requirements document that the user reviews and eventually agrees with. Based on the requirements document, Neo has to suggest an architecture for the RAG system and provide a project breakdown with milestones. The system design goes through another review cycle with the user. After formal approval of the system design, Neo can build the agreed-upon architecture and use the AutoML system to find the optimal RAG hyperparameters for the user. 

Neo can deploy the optimal configuration for the user, test it, and deliver the tested codebase along with documentation back to the user. Security and compliance checks also come in this phase. Finally, Neo enables system monitoring to ensure that the deployed system stays up. Neo also collects user feedback using thumbs up/thumbs down or by showing two responses and asking users to select the better one. Neo keeps a tab of the user interaction touch-points, to assess the maturity of the user he is dealing with to ensure that the documentation is readable and usable at their competence level.

Notice that Neo relied on AutoML capability to optimize the retriever and generation tool. To handle more use cases, Neo must identify each additional tool it requires and build mechanisms to optimize that tool. For instance, imagine that a user, who is a warehouse manager, requests Neo to build a system that identifies the number of humans in a video stream and send an email to the manager in case more than 10 humans are observed in the video. Neo, in this case, would need to get requirements on how many video frames should be checked and then apply the best available object detection model to identify the number of humans. 

*Take me [home](https://sameeurrehman.com/)* 
