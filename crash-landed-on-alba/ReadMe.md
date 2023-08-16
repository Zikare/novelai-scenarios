Crash-Landed on Alba
====================

In an unknown future where humanity still remains split into wealthy and
poor people, you were lucky to be born as the daughter of a rich, interstellar
business mogul. You were lacking nothing, except, perhaps, agency - autonomy.

So you did what any self-respecting spoiled teenager would do and stole your
father's private luxury spacecraft. Your directed the auto pilot to send you
to the furthest habitable planet. That happened to be Alba, a factory farm
with automated orbital defenses.

The wreckage of your spaceship crashed into the farming complex, but you were
forced to flee even from there because the AI prioritizes its crops over
the life of a ship-wrecked survivor.

How can yous survive? What horrors have the ruthless automated farming
systems inflicted on the planet's native flora and fauna?

**Warning: NSFW with creatures possible / likely.**

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
to 'Sarah' but you can to a search and replace in the JSON file or edit it
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
