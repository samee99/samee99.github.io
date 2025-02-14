
Creating a demo for Retrieval Augmented Generation (RAG) is easy, but building a production-grade app is 10x harder, if not more. For every blog and tutorial claiming to get you started with RAG apps or agents in less than an hour, there are hundreds more talking about the complexity of building LLM, and RAG systems that operate reliably at an acceptable accuracy and latency while staying within budget.

So why is this hard? Let's imagine you want to build a production grade RAG pipeline. You first need to build a data parsing and ingestion system. Then you have to embed your parsed data. After that you need to use the appropriate retrieval method and 

Perhaps the naive choice of parameter may work well when asking simple questions over a short document. 

The system is hard to improve, and there are too many parameters to tune by hand, and you need reliable evaluation to measure performance. 



Response quality gets impacted by incorrect retrieval as wel