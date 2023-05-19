# Benchmarking-Awesome-Diffusion-Models
This is the repository of benchmark for text-to-image diffusion models. We used COCO Caption and DrawBench as prompt sets to evluate the models' capacity on generating common and uncommon images. The metrics considered in this repo are: [CLIPScore](https://github.com/jmhessel/clipscore), [Improved Aesthetic Predictor](https://github.com/christophschuhmann/improved-aesthetic-predictor), [ImageReward](https://github.com/THUDM/ImageReward), [Human Preference Score](https://tgxs002.github.io/align_sd_web/), and the explainable detailed metric, ***X-IQE*** introduced in our work. Hope this would help for your study and research.

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
</table>
