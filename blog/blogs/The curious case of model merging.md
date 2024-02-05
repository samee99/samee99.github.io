Over the past month, the LLM community has been obsessed with model merging, a method that combines multiple LLMs into a single one without requiring additional training. It caught my eye on [Twitter](https://twitter.com/maximelabonne/status/1747350120067154227). I wanted to ec Maxime Labonne's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) got me up and running on merging models. 

To get my hands dirty, I tried out 3 different methods for combining LLMs: 
- SLERP [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) 
- TIES  [Samee-ur/NeuralPipe-7B-TIES](https://huggingface.co/Samee-ur/NeuralPipe-7B-TIES)  
- Passthrough [Samee-ur/NeuralPipe-9B-Passthrough](https://huggingface.co/Samee-ur/NeuralPipe-9B-Passthrough)



I then took the [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) model and performed [Direct Preference Optimization](https://arxiv.org/abs/2305.18290) on it using the [Intel/orca_dpo_pairs](https://huggingface.co/datasets/Intel/orca_dpo_pairs) dataset. 


Omer Sanseviero has a [collection on Hugging Face](https://huggingface.co/collections/osanseviero/model-merging-65097893623330a3a51ead66) containing research papers outlining these techniques in detail. 