# ChatGPT-3.5 vs Claude-3
# How LLMs resolve ambiguity
Temporary syntactic ambiguities occur when the beginning of a sentence can have multiple meanings. This experiment reproduces findings from a research paper that uses a previous generation language model, GPT2, and in contrast, investigates how large language models (LLMs) generate sentence completions from given ambiguous inputs. The types of sentence completions that were generated were noun phrases (NP) and sentential complements (S) by two LLMs- GPT3.5 and Claude3. The findings show that Claude generates more sentential complements than GPT and that both models generate more noun phrases overall. 

## The NP/S Ambiguity
I use 20 NP/S temporary ambiguous sentence portions from Grodner et al. (2003) and 20 unique ones that I created, all of which have a NP and S interpretation. Each sentence portion is passed to the LLMs as input for generation. 

## Methods
### LLMs    
I evaluate two English large language models: GPT3.5-turbo and Claude3-haiku.

### Generation    
For experimental consistency, I used the same prompt, temperature, and maximum amount of tokens for both LLMs in the API calls. A temperature of 0.7 was used which was found to be the right amount for generating creative output that also remained realistic. I generate 40 completions, one for each ambiguous sentence portion and replicate the results three times. 

### Classification    
For this method, manual classification of NP/S was required as it is more reliable than the automated classification that was attempted but was not as successful. To classify a completion as a case of an NP or an S, I inspect the dependency label of the locus of ambiguity (direct object → NP; subject → S). Some of the completions formed a complex NP (e.g., a modifier of another noun), which were also labeled as NP. 

<img src="https://github.com/yulia-samoilovich/syntactic-ambiguity/blob/main/table.png?raw=true" width="700" height="250">

## Conclusion
<img src="https://github.com/yulia-samoilovich/syntactic-ambiguity/blob/main/counts.png?raw=true" width="750" height="500">
