[Over the past month](https://twitter.com/maximelabonne/status/1747350120067154227), the LLM community has been obsessed with model merging, a method that combines multiple LLMs into a single one without requiring additional training. I wanted to see what the fuss was about and try my hand at merging some models myself over the weekend. Maxime Labonne's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) got me up and running. 

To get started, I tried 3 different model merging methods: 
- SLERP [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) 
- TIES  [Samee-ur/NeuralPipe-7B-TIES](https://huggingface.co/Samee-ur/NeuralPipe-7B-TIES)  
- Passthrough [Samee-ur/NeuralPipe-9B-Passthrough](https://huggingface.co/Samee-ur/NeuralPipe-9B-Passthrough)

Combining the models was pretty simple using a modified version of [LazyMergeKit](https://colab.research.google.com/drive/147MCAihwKE1-GBfEvTgQ-kWxVQyiJ1pa?usp=sharing) - thanks to Maxime Labonne for the original version. 

While Maxime's [blog post](https://towardsdatascience.com/merge-large-language-models-with-mergekit-2118fb392b54) did talk about SLERP, TIES, and Passthrough, I still couldn't get why these techniques helped the LLM perform better than the base models they combined. So here is an attempt to understand these methods a bit better.  

- SLERP stands for Spherical Linear Interpolation. It's a way to find the path between two points on a (hyper)sphere. Imagine you are traveling from New York to Paris. SLERP would give you the path representing the shortest flight from New York to Paris. When applying SLERP to model merging for LLMs, we would get a new LLM corresponding to a specific point along the path of our metaphorical NY-Paris flight. The point on that path depends on the interpolation parameters we choose. If we don't interpolate at all, we would still be in NY, corresponding to the first base model, if we interpolate all the way, we would be in Paris, corresponding to the second based model, but anywhere along the way we would be on that interpolated path on the hypersphere. As you would expect, SLERP can only be used to merge two models. 
- [TIES](https://arxiv.org/pdf/2306.01708.pdf) stands for Trim, Elect Sign & Merge: As opposed to SLERP, we can use TIES to combine as many LLMs as we want and not just two. In TIES, we first zero all weight values in the base LLMs that are below a certain threshold (trimming).  Then we do an averaging of the base LLMs' model weights while taking into account the sign of the weights. We do this by choosing one sign, (either positive or negative), and only weights with that chosen sign are averaged together to get the merged model weights. Opposite-signed updates are ignored.


I then took the [Samee-ur/NeuralPipe-7B-slerp](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp) model and performed [Direct Preference Optimization](https://huggingface.co/docs/trl/main/en/dpo_trainer) on it using the [Intel/orca_dpo_pairs](https://huggingface.co/datasets/Intel/orca_dpo_pairs) dataset to get the DPO'ed LLM [Samee-ur/NeuralPipe-7B-slerp-DPO](https://huggingface.co/Samee-ur/NeuralPipe-7B-slerp-DPO). 

Model merging does have a history in the research literature and Omer Sanseviero has a [collection on Hugging Face](https://huggingface.co/collections/osanseviero/model-merging-65097893623330a3a51ead66) containing important papers in this space. 




