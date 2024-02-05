**The curious case of model merging** 

February 2024

[Over the past month](https://twitter.com/maximelabonne/status/1747350120067154227), the LLM community has been obsessed with model merging, a method that combines multiple LLMs into a single one without requiring additional training. I wanted to see what the fuss was about and try my hand at merging some models myself over the weekend. Maxime Labonne's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) got me up and running. 

To get started, I tried two different model merging methods: 
- SLERP [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) - this LLM is a combination of [OpenPipe/mistral-ft-optimized-1218](https://huggingface.co/OpenPipe/mistral-ft-optimized-1218) and [mlabonne/NeuralHermes-2.5-Mistral-7B](https://huggingface.co/mlabonne/NeuralHermes-2.5-Mistral-7B)
- TIES  [Samee-ur/NeuralPipe-7B-TIES](https://huggingface.co/Samee-ur/NeuralPipe-7B-TIES)  - this LLM merges [samir-fama/SamirGPT-v1](https://huggingface.co/samir-fama/SamirGPT-v1), [abacusai/Slerp-CM-mist-dpo](https://huggingface.co/abacusai/Slerp-CM-mist-dpo), and [EmbeddedLLM/Mistral-7B-Merge-14-v0.2](https://huggingface.co/EmbeddedLLM/Mistral-7B-Merge-14-v0.2) . 

Combining the models was pretty simple using a modified version of [LazyMergeKit](https://colab.research.google.com/drive/147MCAihwKE1-GBfEvTgQ-kWxVQyiJ1pa?usp=sharing) - thanks to Maxime Labonne for the original version. 

So how do SLERP and TIES model merging work and why do these techniques help the merged LLM perform better than the base models they are built from? Here is an attempt to understand this a bit better.  

- SLERP standing for Spherical Linear Interpolation is a way to find the path between two points on a (hyper)sphere. Imagine you are traveling from New York to Paris. SLERP would give you the path representing the shortest flight from New York to Paris. When applying SLERP to model merging for LLMs, we would get a new LLM corresponding to a specific point along the path of our metaphorical NY-Paris flight. The point on that path depends on the interpolation parameters we choose. If we don't interpolate at all, we would still be in NY, corresponding to the first base model, if we interpolate all the way, we would be in Paris, corresponding to the second based model, but anywhere along the way we would be on that interpolated path on the hypersphere. As you would expect, SLERP can only be used to merge two models. 

- [TIES](https://arxiv.org/pdf/2306.01708.pdf) standing for Trim, Elect Sign, and Merge, is a method to combine multiple LLMs using a fancy form of model weights averaging. With TIES, we first discard weight values from all models that are too small (trimming). Then, we average the remaining weights, but only those that share the same sign, positive or negative, as chosen in the 'elect sign' step. This way, we merge model weights while ensuring consistent sign alignment, disregarding any conflicting weights.


Just for fun, I took the [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) model and performed [Direct Preference Optimization](https://huggingface.co/docs/trl/main/en/dpo_trainer) on it using the [Intel/orca_dpo_pairs](https://huggingface.co/datasets/Intel/orca_dpo_pairs) dataset to get the DPO'ed LLM [Samee-ur/NeuralPipe-7B-slerp-DPO](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp-DPO). I haven't evaluated how much DPO improved performance over the base model in this case. 

Model merging does have a history in the research literature and Omer Sanseviero has a [collection on Hugging Face](https://huggingface.co/collections/osanseviero/model-merging-65097893623330a3a51ead66) containing important papers in this space if you want to learn more. 




