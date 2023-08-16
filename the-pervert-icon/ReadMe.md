The Pervert Icon
================

This scenario puts you in the shoes of Clover, a small-time rock musician
currently going through a remarkable rise. Your band is touring and giving
live performances at venues all over the country.

Live the rock star life, play awesome music, kill it in the interviews and
hang out with your roadies and fans.

*But Clover has a little secret that might kill her career:* after each
stressful performance, she comes close to a nervous breakdown. Her confidence
disappears, her strength fades and she begins to mumble. 

That is not the secret, however. The secret is how she rebounds after a show.
Clover has two best friends, Bowie and Cole, in her motor home. Cuddling
with her two dogs always brings her back from the brink. But her sister
Cecilia is already suspecting that somthing more than cuddling is going on.

**Warning: NSFW with creatures possible / needed.**

Have fun!


NovelAI Usage
-------------

Simply drag the scenario onto your NovelAI browser window or import it.


KoboldAI / KoboldCPP Usage
--------------------------

First, I recommend using KoboldCPP. Simply because it has support for GGML
AI models with 6-bit quantization that hit the sweet spot between too large
`float16` models and too far degraded `GPTQ` 4-bit quantization.

Next, I recommend one of the WizardLM-Uncensored models. WizardLM writes
really beautifully and the uncensored models will not block you from NSFW
actions in your adventure.

Then just load the KoboldAI scenario via the Load button. Your name is fixed
to 'Clover' but you can to a search and replace in the JSON file or edit it
in the introductory text and world info.


**RTX 3090 / RTX 4090 owners:**

For the optimal experience, pick a 13B model with the SuperHOT 8K tuning
applied to have good writing and 8192 tokens context size.

https://huggingface.co/TheBloke/WizardLM-13B-V1-0-Uncensored-SuperHOT-8K-GGML

Launch KoboldCPP like so (*for Linux systems; sorry but I can't help you with
Windows, I don't use it*):

    #!/bin/sh
    model="/insert/your/path/here/wizardlm-13b-v1.0-superhot-8k.ggmlv3.q6_K.bin"
    processorCount=`grep -c ^processor /proc/cpuinfo`

    python koboldcpp.py \
        --threads $processorCount \
        --contextsize 8192 \
        --stream \
        --usecublas \
        --gpulayers 100 \
        --unbantokens \
        --model "$model"

This should lock you to about 21 GiB VRAM usage and give you the best possible
AI quality you can achieve on consumer hardware.

**Big Rig Owners:**

If you have 64+ GiB of RAM and a ThreadRipper or other high-core CPU,
don't shy away from running GPU-based KoboldCPP. On a 32 core system it goes
almost 50% as fast as an RTX 3090 and is just slightly below reading speed.

You may even be able to use the 30B models for even better AI quality.
