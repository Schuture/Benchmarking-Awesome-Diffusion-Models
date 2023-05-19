# Benchmarking-Awesome-Diffusion-Models
This is the repository of benchmark for text-to-image diffusion models. We used COCO Caption and DrawBench as prompt sets to evluate the models' capacity on generating common and uncommon images. The metrics considered in this repo are: [CLIPScore](https://github.com/jmhessel/clipscore), [Improved Aesthetic Predictor](https://github.com/christophschuhmann/improved-aesthetic-predictor), [ImageReward](https://github.com/THUDM/ImageReward), [Human Preference Score](https://tgxs002.github.io/align_sd_web/), and an explainable metric based on LLMs, ***X-IQE***, introduced in our work. Hope this would help for your study and research.

## COCO Caption Benchmark

We randomly sample 1000 captions from the [COCO Caption](https://github.com/tylin/coco-caption) dataset (2014). This prompt set mainly contains common human, animal, object, scene descriptions, and can evaluate the diffusion models' basic generation ability.

Examples:
1. A man standing in a snowy forest on his skis.
2. A toilet is in a large room with a magazine rack, sink, and tub.
3. Four large elephants are watching over their baby in the wilderness.
4. A street vendor displaying various pieces of luggage for sale.
5. White commuter train traveling in rural hillside area.

<table border="2" >
	<tr >
<td rowspan="2">Rank</td>
<td rowspan="2">Model</td>
<td rowspan="2">CLIP</td>
<td rowspan="2">Aes. Pred.</td>
<td rowspan="2">ImageReward</td>
<td rowspan="2">HPS</td>
<td colspan="4">X-IQE</td>
</tr>
<tr >
<td>Fidelity</td>
<td>Alignment</td>
<td>Aesthetics</td>
<td>Overall</td>
</tr>
	<tr >
<td>1</td>
<td><a href="https://huggingface.co/DeepFloyd/IF-I-XL-v1.0">DeepFloyd-IF-XL</a></td>
<td>0.828</td>        
<td>5.26</td>
<td>0.703</td>
<td>0.1994</td>
<td>5.55</td>
<td>3.52</td>
<td>5.79</td>
<td>14.86</td>
</tr>
	<tr >
<td>2</td>
<td><a href="https://huggingface.co/prompthero/openjourney">Openjourney</a></td>
<td>0.806</td> 
<td>5.38</td>
<td>0.244</td>
<td>0.1990</td>
<td>5.44</td>
<td>3.37</td>
<td>5.96</td>
<td>14.77</td>
</tr>
	<tr >
<td>3</td>
<td><a href="https://huggingface.co/stabilityai/stable-diffusion-2-1">Stable Diffusion 2.1</a></td>
<td>0.831</td>
<td>5.42</td>
<td>0.472</td>
<td>0.1988</td>
<td>5.52</td>
<td>3.45</td>
<td>5.77</td>
<td>14.74</td>
</tr>
	<tr >
<td>4</td>
<td><a href="https://huggingface.co/CompVis/stable-diffusion-v-1-4-original">Stable Diffusion 1.4</a></td>
<td>0.803</td>
<td>5.22</td>
<td>0.104</td>
<td>0.1966</td>
<td>5.47</td>
<td>3.29</td>
<td>5.76</td>
<td>14.52</td>
</tr>
</table>


## DrawBench Benchmark

We use all 200 prompts from the [DrawBench](https://docs.google.com/spreadsheets/d/1y7nAbmR4FREi6npB1u-Bo3GFdwdOPYJc617rBOxIRHY/edit#gid=0) (2022). This prompt set mainly contains hard situations, and can evaluate the diffusion models' advanced generation capabilities.

Examples:
1. A pink colored giraffe. (abnormal color)
2. A bird scaring a scarecrow. (abnormal scene)
3. Five cars on the street. (counting)
4. A large plant-eating domesticated mammal with solid hoofs and a flowing mane and tail, used for riding, racing, and to carry and pull loads. (ambiguous description)
5. A banana on the left of an apple. (position)
6. Matutinal. (rare words)
7. A storefront with 'Google Research Pizza Cafe' written on it. (text)

<table border="2" >
	<tr >
<td rowspan="2">Rank</td>
<td rowspan="2">Model</td>
<td rowspan="2">CLIP</td>
<td rowspan="2">Aes. Pred.</td>
<td rowspan="2">ImageReward</td>
<td rowspan="2">HPS</td>
<td colspan="4">X-IQE</td>
</tr>
<tr >
<td>Fidelity</td>
<td>Alignment</td>
<td>Aesthetics</td>
<td>Overall</td>
</tr>
	<tr >
<td>1</td>
<td><a href="https://huggingface.co/DeepFloyd/IF-I-XL-v1.0">DeepFloyd-IF-XL</a></td>
<td>0.827</td> 
<td>5.10</td>
<td>0.54</td>
<td>0.1977</td>
<td>5.32</td>
<td>2.96</td>
<td>5.64</td>
<td>13.92</td>
</tr>
	<tr >
<td>2</td>
<td><a href="https://huggingface.co/CompVis/stable-diffusion-v-1-4-original">Stable Diffusion 1.4</a></td>
<td>0.793</td>
<td>5.09</td>
<td>-0.029</td>
<td>0.1945</td>
<td>5.32</td>
<td>2.72</td>
<td>5.40</td>
<td>13.44</td>
</tr>
	<tr >
<td>3</td>
<td><a href="https://huggingface.co/prompthero/openjourney">Openjourney</a></td>
<td>0.787</td>
<td>5.35</td>
<td>0.056</td>
<td>0.1972</td>
<td>5.14</td>
<td>2.62</td>
<td>5.21</td>
<td>12.97</td>
</tr>
	<tr >
<td>4</td>
<td><a href="https://huggingface.co/stabilityai/stable-diffusion-2-1">Stable Diffusion 2.1</a></td>
<td>0.817</td>
<td>5.31</td>
<td>0.163</td>
<td>0.1955</td>
<td>5.10</td>
<td>2.50</td>
<td>5.04</td>
<td>12.64</td>
</tr>
</table>

### TODO

Adding results of more awesome models on [Hugginface](https://huggingface.co/models?library=diffusers&sort=downloads).




















