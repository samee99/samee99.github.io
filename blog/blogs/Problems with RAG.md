
Creating a demo for Retrieval Augmented Generation (RAG) is easy, but building a production-grade app is 10x harder, if not more. For every blog and tutorial claiming to get you started with RAG apps or agents in less than an hour, there are hundreds more talking about the complexity of building LLM, and RAG systems that operate reliably at an acceptable accuracy and latency while staying within budget.

So why is this hard? Let's imagine you want to build a production grade RAG pipeline. You first need to build an optimal data parsing and ingestion system. Then you have to embed your parsed data using the right embedding model(s). Once the data is ingested, you need to use an appropriate retrieval method and the right LLM with an optimal prompt to get the response you want. 

Every choice you make affects the performance of your RAG pipeline. Typical questions on your mind when building the system would be "which parser is the correct choice for my PDF that has both text and tables in it?", "what is the right chunk size for my use case?", "which embedding model would best fit my needs", "what type of retrieval method should I use", "how many results should I retrieve", "should I use a reranker", "which LLM makes sense for my use case". 

Perhaps the naive choice of parameter may work well when asking simple questions over a short document. 

The system is hard to improve, and there are too many parameters to tune by hand, and you need reliable evaluation to measure performance. 



Response quality gets impacted by incorrect retrieval as wel