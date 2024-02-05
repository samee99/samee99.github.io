Over the past month, there has been a frenzy in the LLM community related to model merging, a method that combines multiple LLMs into a single one. It caught my eye on [Twitter](https://twitter.com/maximelabonne/status/1747350120067154227) and Maxime Labonne's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) got me up and running on merging models. 

To get my hands dirty, I tried out 3 different methods for combining LLMs: 
- SLERP [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp)
- TIES  [Samee-ur/NeuralPipe-7B-TIES](https://huggingface.co/Samee-ur/NeuralPipe-7B-TIES)  
- Passthrough [Samee-ur/NeuralPipe-9B-Passthrough](https://huggingface.co/Samee-ur/NeuralPipe-9B-Passthrough)

I then took the [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) model and performed Direct Preference Optimization on it using the [Intel/orca_dpo_pairs](https://huggingface.co/datasets/Intel/orca_dpo_pairs) dataset. 

Omer Sanseviero has a [collection on Hugging Face](https://huggingface.co/collections/osanseviero/model-merging-65097893623330a3a51ead66) containing research papers outlining these techniques in detail. 