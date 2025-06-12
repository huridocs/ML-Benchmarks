dataset: upr_action (5 labels, single label classification)
model: claude sonnet 3.7

|               Method              | Train/Test Samples | Train Rounds | Average Train Accuracy | Test Set Accuracy |
|-----------------------------------|--------------------|--------------|------------------------|-------------------|
|        contrastive_learning       |     19801/79203    |       6      |          53.28         |       70.25       |
|        constraints_no_regex       |     19801/79203    |       7      |          53.09         |       70.14       |
|       multi_stage_filtering       |     19801/79203    |       6      |          50.95         |       68.85       |
|   constraints_dictionary_mapping  |     19801/79203    |       5      |          41.94         |       68.32       |
|           default prompt          |     19801/79203    |      10      |          51.0          |       67.74       |
|   special_instructions_linguist   |     19801/79203    |       7      |          50.17         |       65.66       |
| special_instructions_no_words_len |     19801/79203    |       7      |          56.59         |       65.55       |
|  special_instructions_robustness  |     19801/79203    |       4      |          49.73         |        65.1       |
|  special_instructions_simplicity  |     19801/79203    |       4      |          39.09         |       61.67       |
|             true_false            |     19801/79203    |       9      |          43.19         |       61.46       |
|           scoring_system          |     19801/79203    |       4      |          46.85         |       53.59       |
|special_instructions_data_scientist|     19801/79203    |       3      |          43.45         |       51.42       |
|          self_reflection          |     19801/79203    |       3      |          40.02         |       50.84       |
|        reverse_engineering        |     19801/79203    |       4      |          40.98         |       49.53       |
|       constraints_only_elif       |     19801/79203    |       8      |          41.36         |        49.5       |
|  constraints_only_substring_match |     19801/79203    |       3      |          33.54         |       42.95       |
|        constraints_no_loops       |     19801/79203    |       5      |          36.44         |        42.9       |
|          chain_of_thought         |     19801/79203    |       2      |          31.8          |       38.47       |
|             same_chat             |     19801/79203    |       3      |          26.38         |       27.07       |


model: gemini2.5-flash

|               Method              | Train/Test Samples | Train Rounds | Average Train Accuracy | Test Set Accuracy |
|-----------------------------------|--------------------|--------------|------------------------|-------------------|
| special_instructions_no_words_len |     19801/79203    |       7      |          12.61         |       25.69       |
|             true_false            |     19801/79203    |      10      |          7.47          |       20.76       |

---


|               Method              |       Model       | Train/Test Samples | Train Rounds | Average Test Accuracy | Best Test Set Accuracy |
|-----------------------------------|-------------------|--------------------|--------------|-----------------------|------------------------|
|             lightgbm              |  gemini2.5-flash  |     19801/79203    |       3      |          85.06        |         85.65          |
|             lightgbm              | claude_sonnet-3.7 |     19801/79203    |       6      |          84.53        |         85.33          |
|           neural network          | claude_sonnet-3.7 |     19801/79203    |       5      |          80.59        |         86.06          |
|           neural network          |  gemini2.5-flash  |     19801/79203    |       4      |          73.87        |         87.46          |
|            word_vectors           | claude_sonnet-3.7 |     19801/79203    |       4      |          59.19        |         73.92          |
|            word_vectors           |  gemini2.5-flash  |     19801/79203    |       3      |          45.65        |         45.65          |

- gemini2.5-flash tends to create similar codes even if we give more examples in the prompt or tell "improve this code".
- At the last step of every method, I tried saying "Improve this code to make the model perform better" on the best code the LLM created in the previous steps, and it mostly helped.
- In gemini2.5-flash's lightgbm method, it created the same code in two passes and when I asked to make the code better, it created a logic for grid search, which gave a better accuracy but a bit slower since it's tuning the parameters.
- In word_vectors, there was no change in gemini2.5-flash even though I told it to improve the code.


- [x] Chain of thought prompting:
    "Before writing the function, carefully think and reason step by step about how to solve the classification task based on the examples. However, only output the final function definition, wrapped in a Python code block, with no explanations or commentary."
- [x] Try to add constraints in prompt:
    - [x] No regular expressions
    - [x] Use dictionaries for mapping
    - [x] Use only if/else
    - [x] No loops
    - [x] Substring matching only (Only use substring matching (e.g., `in` operator) to determine topic assignments. Do not use full-word or token-based matching.)

- [x] Try scoring system:
    "Implement a scoring system in your function. For each topic label, assign a score based on how well the input text matches that topic, using any logic you infer from the examples. After scoring all labels, select the label with the highest score. If no label has a positive score, return an empty list."

- [x] Special instructions:
    - [x] "Write the function as if you were a linguist, focusing on subtle language cues." (logs_special_instructions_linguist.md)
    - [x] "Imagine you are a data scientist optimizing for maximum accuracy, even if the code is complex." (logs_special_instructions_data_scientist.md)
    - [x] "Write the function as if you were preparing it for a production system where robustness is critical." (logs_special_instructions_robustness.md)
    - [x] "Write the function as if you are teaching a beginner, prioritizing clarity and simplicity." (logs_special_instructions_simplicity.md)

- [x] Try to use the same chat.

- [x] Self consistency/reflection: Ask the LLM to double-check its own logic:
    "First, write your function as usual. Then, review your function and describe any potential weaknesses, edge cases, or improvements. If you find any issues, revise your function accordingly.  
**Important:** Only output the final, revised function definition, wrapped in a Python code block, with no explanations or commentary outside the code block."

- [x] Reverse engineering:
    "You are only given the input texts and their assigned topic labels, but not the explicit rules. Your task is to reverse engineer the possible logic that could have produced these labels, and write a function that mimics this logic as closely as possible."

- [x] Multi Stage Filtering:
    "Write your function in two stages: first, filter out any topics that are clearly irrelevant to the input text; then, from the remaining topics, select the most appropriate one using more detailed logic."

- [x] Contrastive Learning:
    "Compare the input text to all provided examples. Assign the label whose example is most similar in both intent and specificity."
