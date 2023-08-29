Coming of Age
=============

As the name implies, this is a coming-of-age story where you are a young woman
still living in her parents' house. Soon you will finish your studies and go
looking for a job, possibly in another city.

But until then, your perfectly average life could well be upended by strange
events, not least of which is your neighbor Dave who you can't quite decide if
he's an awkward but friendly loner or a weird creep. At least he has two large
and friendly dogs. Too friendly... sometimes.

Then there's the old, nosy lady from the other side of street who keeps picking
through your trash and making it her business that people keep their properties
in order.

Laze about in your perfectly average life or start living, it's your choice.

**Warning: NSFW with creatures possible / likely.**

Have fun!


NovelAI Usage
-------------

Simply drag the scenario onto your NovelAI browser window or import it.

When you play, you may eventually encounter a weird girl that is looking
for you, precisely because of your infamy.

She has two lorebook entries. If you accept her proposal, you should then
open the lorebook, turn off "Kassie (Before Meeting)" and enable the other
entry, titled "Kassie (After Meeting)".

Or just disable them both before starting your adventure if you want to play
as a solo adventurer or make up your own story.


KoboldAI / KoboldCPP Usage
--------------------------

First, I recommend using KoboldCPP. Simply because it has support for GGML
AI models with 6-bit quantization that hit the sweet spot between too large
`float16` models and too far degraded `GPTQ` 4-bit quantization.

Next, I recommend one of the WizardLM-Uncensored models. WizardLM writes
really beautifully and the uncensored models will not block you from NSFW
actions in your adventure.

Then just load the KoboldAI scenario via the Load button. Your name is fixed
to 'Brian' but you can to a search and replace in the JSON file or edit it
in the introductory text and world info.

The world info contains entries for a girl that is looking for you, precisely
because of your infamy. If you want her, first permanently enable
the `nokassie` entry in your world info, then, once the random encounter
took place (and you accepted her proposal), turn it off and enable
the `joinedkassie` entry instead.


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
