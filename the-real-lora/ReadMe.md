The Real Lora
=============

A vanilla mind control scenario. You are a rich dude with a mansion, a wife
and two adult daughters. All your money comes from investments and you are
plainly and simply bored.

You have acquired an illegal 'Lora Crown' - it is like the neural network
overlays used in AI technology, but instead superimposes virtual neural
connections on a real brain. This amazing device can temporarily give anyone
the knowledge of a world class expert.

Does that sound too good to be true? It is. Before the device even went past
the prototype stage, it became obvious that it could be used for all kinds of
devious purposes - from assassinations, to false confessions and even carnal
things such as temporarily turning people into willing sex slaves.

What will you do with such a highly illegal and dangerous device?
How bored are you with your life?

**Warning: NSFW with creatures possible, incest possible.**

Have fun!


NovelAI Usage
-------------

Simply drag the scenario onto your NovelAI browser window or import it.

Your 'Lora Crown' has a few templates that you can upload to it. Just make
sure to explicitly state which template is active to prevent the AI from
getting confused about the effect the headband is supposed to have.


KoboldAI / KoboldCPP Usage
--------------------------

First, I recommend using KoboldCPP. Simply because it has support for GGML
AI models with 6-bit quantization that hit the sweet spot between too large
`float16` models and too far degraded `GPTQ` 4-bit quantization.

Next, I recommend one of the WizardLM-Uncensored models. WizardLM writes
really beautifully and the uncensored models will not block you from NSFW
actions in your adventure.

Then just load the KoboldAI scenario via the Load button. Your name is fixed
to 'Gideon' but you can to a search and replace in the JSON file or edit it
in the introductory text and world info.

Your 'Lora Crown' has a few templates that you can upload to it. Just make
sure to explicitly state which template is active to prevent the AI from
getting confused about the effect the headband is supposed to have.


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
