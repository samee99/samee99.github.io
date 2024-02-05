[Over the past month](https://twitter.com/maximelabonne/status/1747350120067154227), the LLM community has been obsessed with model merging, a method that combines multiple LLMs into a single one without requiring additional training. I wanted to see what the fuss was about and try my hand at merging some models myself. Maxime Labonne's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) got me up and running. 

To get started, I tried 3 different model merging methods: 
- SLERP [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) 
- TIES  [Samee-ur/NeuralPipe-7B-TIES](https://huggingface.co/Samee-ur/NeuralPipe-7B-TIES)  
- Passthrough [Samee-ur/NeuralPipe-9B-Passthrough](https://huggingface.co/Samee-ur/NeuralPipe-9B-Passthrough)

Combining the models was pretty simple using a modified version of [LazyMergeKit](https://colab.research.google.com/drive/147MCAihwKE1-GBfEvTgQ-kWxVQyiJ1pa?usp=sharing) - thanks to Maxime Labonne for the original version. 

While Maxime's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) did talk about SLERP, TIES, and Passthrough, I still couldn't get why these techniques helped the LLM perform better than the base models they combined. So here is an attempt to understand these methods a bit better.  

SLERP - 


I then took the [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) model and performed [Direct Preference Optimization](https://huggingface.co/docs/trl/main/en/dpo_trainer) on it using the [Intel/orca_dpo_pairs](https://huggingface.co/datasets/Intel/orca_dpo_pairs) dataset to get the DPO'ed LLM [Samee-ur/NeuralPipe-7B-slerp-DPO](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp-DPO). 

Model merging does have a history in the research literature and Omer Sanseviero has a [collection on Hugging Face](https://huggingface.co/collections/osanseviero/model-merging-65097893623330a3a51ead66) containing important papers in this space. 




