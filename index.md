---
layout: page
title: Home
---

<section class="intro">
<p class="intro-text"></p>
</section>

<hr class="break">

## Current Status

I recently received a [grant](https://blog.cosmos-institute.org/p/announcing-80-new-cosmos-grantees) from the [Cosmos Institute](https://cosmos-institute.org) to build the <b>Compression Integrity Bench</b>.

<img src="pictures/Jarrett Vickers — Compression Integrity Bench.png" alt="Compression Integrity Bench" style="max-width: 100%; height: auto; margin-top: 10px;">

>_Decentralized AI is premised on open-weight models running on local hardware. But almost nobody runs them at full precision. LLM deployments are implemented under various inference optimization regimes, such as quantization. Quantized LLM deployments are evaluated on task performance, but not on epistemic behavior. Careless quantization does more than just degrade performance - it disproportionately affects low-magnitude weights and the tails of the output distribution. If hedging, alternative hypotheses, and dissent live in those tails, then quantization could cause epistemic degradation. If this compromises the ability of open-weight models to maintain epistemic integrity, then the promise of decentralized AI may remain unrealized._

>_LLM epistemic integrity - such as calibrated uncertainty, (resistance to) sycophancy, willingness to perform Bayesian updates, use of references, and steelmanning opposition - are all implemented late in the LLM training process, in post-training. Research has shown that post-trained behaviors degrade under quantization, which suggests that epistemic integrity may be compromised. LLM epistemic integrity under quantization has never been rigorously researched and documented. You should be able to know if the local model you chose behaves faithfully to the one you think you're running._

<br/>
<br/>
In my spare time, I teach machine learning at [Network School](https://ns.com/) in Astana, Kazakhstan.

<hr class="break">

## Projects

<div class="project">
    <h3>Quantization Study</h3>
        <p>I ran a <a href="https://github.com/JR-Vickers/quantization-study" target="_blank" rel="noopener">quantization study</a> on an open-source coding model, DeepSeek-Coder-V2-Lite-Instruct.</p>
        <p>The goals of this project were to 1) teach myself inference engineering by jumping into the deep end of the pool, and 2) extensively document this process in a series of notebooks so that I could use them to teach inference engineering to others.</p>
        <p>The intent was to quantize the model as heavily as possible without degrading performance too badly.  Quantizing from 16-bit to 8-bit integers had minimal impact on the HumanEval results, while substantially reducing model size and increasing token/sec.  We see more model errors at 4-bit quantization, which I was able to mitigate by running sensitivity analyses on each layer and identifying which layers degenerated performance the most under 4-bit quantization.  This led me to create a mixed-precision policy, in which four layers were left at 8-bit quantization while the others were set to 4-bit.  The result was a model that was only marginally larger than the pure 4-bit version, while reclaiming much of the lost HumanEval Pass@1 performance.</p>
        <img src="pictures/quantization_results.png" alt="Quantization study results" style="max-width:100%; height:auto; margin-top:10px;">
</div>

<div class="project">
    <h3>Does GRAM's Knowledge Isolation Survive Quantization?</h3>
    <p>
        In July, AE Studios and Anthropic joint published a new model architecture for technical alignment called <a href="https://github.com/JR-Vickers/modular-pretraining" target="_blank" rel="noopener">Gradient Routed Auxiliary Modules (GRAM)</a>.  The idea is to separate knowledge of dual-use technologies (such as nuclear, biotech, etc.) into separate modules during pretraining, which can then be ablated at inference.
    </p>
    <p>
        Many technical alignment solutions have been shown to degrade under quantization and other inference optimizations, so <a href="https://github.com/JR-Vickers/modular-pretraining" target="_blank" rel="noopener">I tested whether this was the case for GRAM</a>.  They didn't publish the weights of the model they trained, but they did publish the exact methodology they used to train it.  It's a small 26m param model, so I was able to train my own model that performed the same as theirs.
    </p>
    <p>
        I ran some evals to establish a baseline, then started quantizing.  From the results:
    </p>
    <p>
        At int4, signed capability recovery was <b>−77.48%</b> and signed isolation erosion was
        <b>1.97%</b>, both below the pre-registered 20% thresholds. Mean retained-topic loss rose
        <b>5.46%</b>, below the 10% general-degradation guard. Negative recovery means the quantized,
        ablated model moved farther from the FP32 active reference; it is not a claim that
        quantization improved knowledge removal.
    </p>
    <img src="pictures/gram_results.png" alt="GRAM results" style="max-width:100%; height:auto; margin-top:10px;">
</div>

<div class="project">
<p>At <a href="https://ns.com/" target="_blank" rel="noopener">Network School</a>, I <a href="https://x.com/0xJarrett/status/1959995784872841452" target="_blank" rel="noopener">taught a robotics class</a> with my co-host <a href="https://www.linkedin.com/in/lana-shevchenko/" target="_blank" rel="noopener">Lana</a>.  We were able to take a room of complete robotics novices and had them assemble and program a series of <a href="https://github.com/TheRobotStudio/SO-ARM100" target="_blank" rel="noopener">SO-ARM100 robotic arms</a> in just a few hours.  Our students also learned how to operate a 3D printer.</p>
<img src="pictures/robotics_learnathon.png" alt="Robotics learnathon class" style="max-width: 100%; height: auto; margin-top: 10px;">
</div>

<div class="project">
<p><a href="https://www.kaggle.com/code/bjrnste/path-to-the-amazon-sun-gods#2.-Download-the-Terrabrasilis-deforestation-data-&-Define-the-AOI-around-the-Indigenous-Territories-uncovered-above" target="_blank" rel="noopener">My team's submission</a> for the <a href="https://openai.com/openai-to-z-challenge/" target="_blank" rel="noopener">OpenAI-to-Z challenge</a>.  Process large amounts of satellite data to scan the Amazonian rainforest for undiscovered ruins and earthworks.  A Jupyter notebook that utilizes essential data science tools such as numpy, pandas, matplotlib, and more niche tooling such as geopandas and rasterio.  Large-scale image classification.</p>
</div>

<hr class="break">

## Recent work history

[Rainmaker Technology Corporation](https://www.rainmaker.com/) - Forward Deployed Engineer
