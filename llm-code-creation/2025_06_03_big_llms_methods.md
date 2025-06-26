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


dataset: upr_action (5 labels, single label classification)
model: gemini2.5-flash

|               Method              | Train/Test Samples | Train Rounds | Average Train Accuracy | Test Set Accuracy |
|-----------------------------------|--------------------|--------------|------------------------|-------------------|
| special_instructions_no_words_len |     19801/79203    |       7      |          12.61         |       25.69       |
|             true_false            |     19801/79203    |      10      |          7.47          |       20.76       |

---
---

dataset: upr_action (5 labels, single label classification)

|               Method              |       Model       | Train/Test Samples | Train Rounds | Average Test Accuracy | Best Test Set Accuracy | Average Time Train+Test (s)
|-----------------------------------|-------------------|--------------------|--------------|-----------------------|------------------------|----------------------------|
|       TextSingleLabelSetFit       |      (no llm)     |     19801/79203    |       -      |          89.54        |         89.54          |          450               |
|     pretrained_transformers       |  gemini2.5-flash  |     19801/79203    |       4      |          89.53        |         89.76          |          1150.19           |
|             nn_bilstm             |  gemini2.5-flash  |     19801/79203    |       4      |          87.39        |         88.25          |          1229.37           |
|     nn_hierarchical_attention     |  gemini2.5-flash  |     19801/79203    |       3      |          85.66        |         87.75          |          3052.18           |
|             lightgbm              |  gemini2.5-flash  |     19801/79203    |       3      |          85.06        |         85.65          |          980.67            |
|             lightgbm              | claude_sonnet-3.7 |     19801/79203    |       6      |          84.53        |         85.33          |                            |
|        nn_capsule_network         |  gemini2.5-flash  |     19801/79203    |       1*     |          83.03        |         83.03          |          3185.02           |
|      neural_network_attention     |  gemini2.5-flash  |     19801/79203    |       4      |          82.55        |         88.56          |          726.25            |
|           neural network          | claude_sonnet-3.7 |     19801/79203    |       5      |          80.59        |         86.06          |                            |
|         neural_network_cnn        |  gemini2.5-flash  |     19801/79203    |       5      |          76.37        |         84.57          |          926.49            |
|           neural_network          |  gemini2.5-flash  |     19801/79203    |       4      |          73.87        |         87.46          |          3341.14           |
|        neural_network_dense       |  gemini2.5-flash  |     19801/79203    |       4      |          67.75        |         82.96          |          134.04            |
|         neural_network_gru        |  gemini2.5-flash  |     19801/79203    |       4      |          64.19        |         88.27          |          2326.92           |
|             nn_setfit             |  gemini2.5-flash  |     19801/79203    |       1*     |          60.45        |         60.45          |                            |
|            word_vectors           | claude_sonnet-3.7 |     19801/79203    |       4      |          59.19        |         73.92          |                            |
|            word_vectors           |  gemini2.5-flash  |     19801/79203    |       3      |          45.65        |         45.65          |          313.73            |
|        neural_network_lstm        |  gemini2.5-flash  |     19801/79203    |       4      |          35.13        |         39.65          |                            |
|         latest_best_model         | claude_sonnet-3.7 |     19801/79203    |       1*     |          17.43        |         17.43          |          12499             |


- None of these methods performed better than the setfit method we already have.
- gemini2.5-flash tends to create similar codes even if we give more examples in the prompt or tell "improve this code".
- At the last step of every method, I tried saying "Improve this code to make the model perform better" on the best code the LLM created in the previous steps, and it mostly helped.
- In "capsule network" method, it was taking too much time so I stopped it manually, only tried 1 round.
- In "nn_setfit" method, the model created errors in the code, I asked it to fix these errors again and again but it was not able to accomplish it. So, I only run it once.
- In "latest_best_model" method, what I have done is I asked model to "check for the best existing model for this task and use it". But sonnet-3.7 somehow decided to use SVM. gemini2.5-flash on the other hand, decided to use "bert-base-uncased", which I already tried in "pretrained_methods", so I didn't try it again.
- In gemini2.5-flash's lightgbm method, it created the same code in two passes and when I asked to make the code better, it created a logic for grid search, which gave a better accuracy but a bit slower since it's tuning the parameters.
- In word_vectors, there was no change in gemini2.5-flash even though I told it to improve the code.

---
---

dataset: plan_topics (16 labels, multi label classification)

|          Method                 |      Model      | Train/Test Samples  | Train Rounds | Average F1 Score [micro] | Average F1 Score [macro] | Average F1 Score [weighted] | Best F1 Score [micro] | Average Time (s)
|---------------------------------|-----------------|---------------------|--------------|--------------------------|--------------------------|-----------------------------|-----------------------|-----------------|
|     pretrained_transformers     | gemini2.5-flash |     43281/173124    |       3      |           90.74          |           86.15          |            90.61            |         90.83         |     4539.99     |
| pretrained_transformers_thinking| gemini2.5-flash |     43281/173124    |       2      |           90.62          |           87.2           |            90.54            |         91.09         |      2407       |
|        nn_bilstm                | gemini2.5-flash |     43281/173124    |       3      |           85.9           |           79.13          |            85.58            |         86.46         |     1325.63     |
|   nn_hierarchical_attention     | gemini2.5-flash |     43281/173124    |       3      |           85.2           |           77.04          |            84.78            |         86.25         |     1671.7      |
|            lightgbm             | gemini2.5-flash |     43281/173124    |       3      |           83.86          |           72.11          |            82.82            |         83.86         |     2071.92     |
|     TextSetFitMultilingual      |     (no llm)    |     43281/173124    |       -      |           78.6           |           60.74          |            76.07            |         78.60         |     746.72      |
|      TextBalancedSetFit         |     (no llm)    |     43281/173124    |       -      |           76.92          |           67.12          |            76.01            |         76.92         |     359.89      |
|          nn_attention           | gemini2.5-flash |     43281/173124    |       3      |           68.57          |           29.45          |            57.53            |         84.61         |     361.88      |
|     TextSingleLabelSetFit       |     (no llm)    |     43281/173124    |       -      |           64.79          |           37.51          |            59.95            |         64.79         |     500.43      |


---
---

dataset: upr_issues (69 labels, multi label classification)

|             Method             |      Model      | Train/Test Samples | Train Rounds | Average F1 Score [micro] | Average F1 Score [macro] | Average F1 Score [weighted] | Best F1 Score [micro] | Average Time (s) 
|--------------------------------|-----------------|--------------------|--------------|--------------------------|--------------------------|-----------------------------|-----------------------|-----------------|
|     pretrained_transformers    | gemini2.5-flash |     19762/79046    |       3      |           87.72          |           61.03          |            85.75            |         88.11         |     908.71      |
|            lightgbm            | gemini2.5-flash |     19762/79046    |       2      |           85.41          |           64.12          |            84.19            |         85.52         |     5146.03     |
|pretrained_transformers_thinking| gemini2.5-flash |     19762/79046    |       3      |           84.94          |           49.27          |            80.85            |         88.45         |      647.2      |
|          nn_attention          | gemini2.5-flash |     19762/79046    |       2      |           84.05          |           62.12          |            83.21            |         84.41         |     5767.02     |
|      TextSetFitMultilingual    |     (no llm)    |     19762/79046    |       -      |           80.99          |           57.05          |            78.63            |         80.99         |     734.52      |
|        TextBalancedSetFit      |     (no llm)    |     19762/79046    |       -      |           80.22          |           64.24          |            79.94            |         80.22         |     442.82      |
|    nn_hierarchical_attention   | gemini2.5-flash |     19762/79046    |       3      |           76.01          |           46.35          |             72.0            |         84.47         |     116.57      |
|            nn_bilstm           | gemini2.5-flash |     19762/79046    |       3      |           70.58          |           44.7           |            73.49            |         85.19         |     169.78      |
|     TextSingleLabelSetFit      |     (no llm)    |     19762/79046    |       -      |           58.60          |           46.54          |            56.06            |         58.60         |     411.35      |


- As the code becomes more complex, the models tend to create errors in these codes. And it helps a lot if we give some error examples in the prompt and tell the model to avoid them.
- If the models create errors in the code even in the prompt we tell them, if we resend the code and say "From this code, I'm getting this error, fix it" they mostly fix that problem.
- But sometimes the error is not solved and if we get the same error 3-4 times consecutively, most of the time this means it's not going to be solved.
- Activating the models' thinking capability did not help, but it's also not worse. But it can help to detect the errors in the code better.


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

- [x] True/False:
    "For each possible label, write logic that determines whether the input text matches that label (True/False). Evaluate the input text against all label conditions. If only one label condition returns True, assign that label. If multiple label conditions return True, select the label that is the most specific or most appropriate, based on the input and the examples. If none of the label conditions are True return `None` or empty string."

- [x] Don't consider "words" length:
    "Do not create a heuristic, a check based on words count of the given sample."

- [x] LightGBM
- [x] Word vectors
- [x] Try feeding previous code/ask for improvement
- [x] Neural networks
    - [x] Dense
    - [x] CNN
    - [x] LSTM
    - [x] BiLSTM
    - [x] GRU
    - [x] Capsule Network
    - [x] Setfit
    - [x] Attention
    - [x] Hierarchical Attention
    - [x] Pretrained Transformers
    - [x] Latest best model
- [x] XGBoost

- [x] Multilabel Tasks