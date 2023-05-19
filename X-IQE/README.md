# X-IQE: eXplainable Image Quality Evaluation

If you want to run the evaluation demo on your own, please use the AI-generated images and their corresponding prompts here. 
And chat with the [online MiniGPT-4](https://huggingface.co/spaces/Vision-CAIR/minigpt4) with ***Temperature=0.1*** and the following prompts:


### Fidelity Prompt
```
You are my assistant to evaluate the image quality. Briefly describe (within 50 words)
the type (e.g., photo, painting) and content of this image, and analyze whether this image
meets the following conditions of an AI-generated image (within 30 words per point).

1. Imperfect details: distorted, blurry, or irrational faces, limbs, fingers, objects,
or texts.
2. Improper composition: some misplaced object relationships.
3. Strange colors: overly bright, saturated colors.
4. Artificial look: looks like a real image but has an unclear rendering or other artificial
look.

Provide your analysis in JSON format with the following keys: Image description,
Imperfect details, Improper composition, Strange colors, Artificial look, Fidelity
(e.g., 6/10). The fidelity scoring criteria are as follows:

Definitely AI-generated (0-1)
Very likely AI-generated (2-3)
Certain probability of AI generation (4)
Unsure (5)
Certain probability being real (6)
Very real (7-8)
Definitely real (9-10)
```

### Alignment Prompt
```
According to the image and your previous description, how well does the image align
with the following description?

<Prompt for generating this image>

not match at all (1)
Has significant discrepancies (2)
Has several minor discrepancies (3)
Has a few minor discrepancies (4)
Matches exactly (5)

Provide your analysis in JSON format with the following keys: Alignment analysis
(within 100 words), Alignment score (e.g., 4/5).
```

### Aesthetics Prompt
```
Briefly analyze the aesthetic elements of this image (each item within 20 words) and
score its aesthetics. The scoring criteria for each item are as follows.

Extremely bad (0-1)
Poor quality (2-3)
Below average (4)
Average (5)
Above average (6)
Good (7-8)
Excellent (9)
Wonderful (10)

Provide your analysis in JSON format with the following keys: Color harmony,
Color brightness, Color saturation, Composition, Perspective, Light and shadow,
Detailed expression, Vivid posture, Visual impact, Overall aesthetic score (e.g., 6/10).
```


