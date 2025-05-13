
| Task                     | Train/Test Size |
|--------------------------|-----------------|
| upr_paragraph_countries  | 3/15            |
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

- For the above tasks, all of them have given 100% accuracy.
- The hardest tasks in here are "rightstaging_title" and "upr_paragraph_countries". In rightstaging_title, we send model the content of the first page and it figures out the title of that document by merging different parts of the content. So even with just the content information, they done it perfect. And the hard part in upr_paragraph_countries task is, some countries have different spellings sometimes but model has to figure out the correct version from the list of options we gave it, and they done it perfectly.
- I didn't even need to fix the what these models output. So there was no need for a second iteration to lead the models to make them give the answer correctly/in the correct format.
- About the models:
    - ChatGPT 4.1 works pretty consistent and understands well the prompt. Like, if we say "don't do any explanations" and so on, it just gives the output with a perfect accuracy and that's it. It's speed is medium-fast compared to others.
    - Claude Sonnet 3.7 tends to create comments even if we tell it not to do. And I saw some comments about this model saying Sonnet 3.5 was better to achieve these kinds of tasks, Sonnet 3.7 just wants to talk more. But still, it gives the correct answers in the end. As for speed, it's slower than the others - because of it's thinking process.
    - Gemini 2.5 Flash is a very decent model and works pretty fast most of the time. But this model needed some kind of guidance in 1 case. What it outputted was not wrong and actually could be acceptable but it was just not the complete answer as we have in the labels.
    - Deepseek v3.1. Second fastest model I have seen, pretty decent model. No problems, just working perfectly.
    - Grok 3. Very fast, most of the time it's actually the fastest one and it works perfectly, no problems.
    - Llama 4 Maverick works fast but slower than Deepseek and Grok. Also it tends to create comments more than Deepseek and Grok but still gives the correct answers, works pretty well.
    - Qwen3 235b A22B is the slowest one here because of it's thinking process. It just talks to itself like it's having a monologue but at the end of this monologue it gives the correct answers. Was fun to watch it and actually a good model but requires a lots of time.

As a summary:
- Deepseek v3.1 and Grok 3 are the fastest models, they work perfectly, didn't require more guidance - more samples than I have provided.
- ChatGPT 4.1, Gemini 2.5 Flash an Llama 4 Maverick also are good, they are consistent but a bit slower than Deepseek and Grok 3.
- We should'nt use Claude Sonnet 3.7 and Qwen3 235b A22B. They take a lof of time even though they give the correct answers.

---

Details about the data I have used:

upr_paragraph_countries (no code)  
train samples: 118.1, 118.2, 118.4  
test samples: 118.3/5/6/7/8/9/10/11/12/13/14/15/16/18/19

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
