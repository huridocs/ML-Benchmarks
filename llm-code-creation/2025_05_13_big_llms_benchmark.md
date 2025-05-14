
| Model                |  Context Window     |
|----------------------|---------------------|
| ChatGPT 4.1          | 1M tokens           |
| Claude Sonnet 3.7    | 200K tokens         |
| Gemini 2.5 Flash     | 1M tokens           |
| DeepSeek v3.1        | 128K–200K tokens    |
| Grok 3               | 128K+ tokens        |
| Llama4 Maverick      | 128K+ tokens        |
| Qwen3 235b A22B      | 128K–200K tokens    |




| Task                     | Train/Test Size |
|--------------------------|-----------------|
| upr_paragraph_countries  | 3/19            |
| upr_paragraph_text       | 3/15            |
| rightstaging_symbol      | 3/15            |
| rightstaging_title       | 3/15            |
| vote_against_english     | 3/12            |
| vote_abstaining_english  | 3/12            |
---
- I have tried these models:
    - ChatGPT 4.1
    - Claude Sonnet 3.7
    - Gemini 2.5 Flash
    - DeepSeek v3.1
    - Grok 3
    - Llama4 Maverick
    - Qwen3 235b A22B

Notes:

- For the above tasks, all of them have given 100% accuracy. (Except Llama4 Maverick has a 1 mistake in upr_paragraph_countries, details are below)
- The hardest tasks in here are "rightstaging_title" and "upr_paragraph_countries". In rightstaging_title, we send model the content of the first page and it figures out the title of that document by merging different parts of the content. So even with just the content information, they done it perfect. And the hard part in upr_paragraph_countries task is, some countries have different spellings sometimes but model has to figure out the correct version from the list of options we gave it. In some hard cases (118.44 and 118.71), only ChatGPT and Sonnet 3.7 was able to give the correct answers at the first pass. Gemini 2.5 Flash, DeepSeek v3.1, Grok 3 all failed in 118.44 but when we feed it this mistake as an example in the prompt, they fixed it. Unfortunately Llama4 Maverick failed in both of these cases and was not able to fix 118.71 even though we pass it in the prompt.
- I didn't even need to fix the what these models output. So there was no need for a second iteration to lead the models to make them give the answer correctly/in the correct format.
- About the models:
    - ChatGPT 4.1 works pretty consistent and understands well the prompt. Like, if we say "don't do any explanations" and so on, it just gives the output with a perfect accuracy and that's it. It's speed is medium-fast compared to others.
    - Claude Sonnet 3.7 tends to create comments even if we tell it not to do, so it's a bit slower. But it understood what we wanted and gave always the correct answers at first pass. 
    - Gemini 2.5 Flash is a very decent model and works pretty fast most of the time. But this model depends more on the prompt, so it may need more guidance. But as long as we are able to provide the proper examples, it'll update itself and will not do mistakes.
    - Deepseek v3.1. Second fastest model I have seen, pretty decent model. No problems, just works great.
    - Grok 3. Very fast, most of the time it's actually the fastest one and it works pretty good.
    - Llama 4 Maverick works fast but slower than Deepseek and Grok. Also it tends to create comments more than Deepseek and Grok but still gives the correct answers most of the time. But as I mentioned above, it failed to understand the mistake it did and was not able to fix it in one case, so, probably we shouldn't use this.
    - Qwen3 235b A22B is the slowest one here because of it's thinking process. It just talks to itself like it's having a monologue but at the end of this monologue it gives the correct answers. Was fun to watch it and actually a good model but requires a lots of time.

As a summary:
- ChatGPT 4.1 feels like the safest option around the above models. It always gave the correct answers at first pass, understands that there shouldn't be comments etc. and it's speed is fine.
- Deepseek v3.1 and Grok 3 are the fastest models, they work pretty good, didn't require much guidance, only in a single case they required it and they fixed it.
- Gemini 2.5 Flash is also a good & fast model. But it may require more guidance than DeepSeek v3.1 and Grok 3.
- Llama 4 Maverick is also not bad but since it was not able to fix the mistake even though we provided it in the prompt (even it's just a single case), I think we should just skip it. Otherwise it's not a bad model and works fast, decently.
- We should'nt use Claude Sonnet 3.7 and Qwen3 235b A22B especially if we care about the time. They take a lof of time even though they give the correct answers.

---

Details about the data I have used:

upr_paragraph_countries (no code)  
train samples: 118.1, 118.2, 118.4  
test samples: 118.3/5/6/7/8/9/10/11/12/13/14/15/16/18/19/44/59/71/74

upr paragraph text  
train samples: 118.1, 118.2, 118.7  
test samples: 118.3/4/5/6/8/9/10/11/12/13/14/15/16/17/18

rightstaging symbol  
train samples: A/HRC/40/78,77,76  
test samples: A/HRC/40/75,74,72,71,70,69,67,65,64,62,61,60,59,58,56

rightstaging titles  
train samples: A/HRC/38/37, A/HRC/39/11, A/HRC/40/76"  
test samples: 40|78/77/75/74/72/71/70/69/67/65/64/62/61/60/59


vote against english  
train samples: first three  
test samples: the rest of the samples


vote abstaining english  
train samples: first three  
test samples: the rest of the samples
