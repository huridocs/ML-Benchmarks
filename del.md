|               Method              |       Model       | Train/Test Samples | Train Rounds | Average Train Accuracy | Test Set Accuracy |
|-----------------------------------|-------------------|--------------------|--------------|------------------------|-------------------|
|              lightgbm             | claude_sonnet-3.7 |     19801/79203    |       5      |          84.41         |       84.35       |
|        contrastive_learning       | claude_sonnet-3.7 |     19801/79203    |       6      |          53.28         |       70.25       |
|        constraints_no_regex       | claude_sonnet-3.7 |     19801/79203    |       7      |          53.09         |       70.14       |
|       multi_stage_filtering       | claude_sonnet-3.7 |     19801/79203    |       6      |          50.95         |       68.85       |
|   constraints_dictionary_mapping  | claude_sonnet-3.7 |     19801/79203    |       5      |          41.94         |       68.32       |
|                logs               | claude_sonnet-3.7 |     19801/79203    |      10      |          51.0          |       67.74       |
|   special_instructions_linguist   | claude_sonnet-3.7 |     19801/79203    |       7      |          50.17         |       65.66       |
| special_instructions_no_words_len | claude_sonnet-3.7 |     19801/79203    |       7      |          56.59         |       65.55       |
|  special_instructions_robustness  | claude_sonnet-3.7 |     19801/79203    |       4      |          49.73         |        65.1       |
|  special_instructions_simplicity  | claude_sonnet-3.7 |     19801/79203    |       4      |          39.09         |       61.67       |
|             true_false            | claude_sonnet-3.7 |     19801/79203    |       9      |          43.19         |       61.46       |
|           scoring_system          | claude_sonnet-3.7 |     19801/79203    |       4      |          46.85         |       53.59       |
|special_instructions_data_scientist| claude_sonnet-3.7 |     19801/79203    |       3      |          43.45         |       51.42       |
|          self_reflection          | claude_sonnet-3.7 |     19801/79203    |       3      |          40.02         |       50.84       |
|        reverse_engineering        | claude_sonnet-3.7 |     19801/79203    |       4      |          40.98         |       49.53       |
|       constraints_only_elif       | claude_sonnet-3.7 |     19801/79203    |       8      |          41.36         |        49.5       |
|            word_vectors           | claude_sonnet-3.7 |     19801/79203    |       3      |          63.7          |       45.65       |
|  constraints_only_substring_match | claude_sonnet-3.7 |     19801/79203    |       3      |          33.54         |       42.95       |
|        constraints_no_loops       | claude_sonnet-3.7 |     19801/79203    |       5      |          36.44         |        42.9       |
|          chain_of_thought         | claude_sonnet-3.7 |     19801/79203    |       2      |          31.8          |       38.47       |
|             same_chat             | claude_sonnet-3.7 |     19801/79203    |       3      |          26.38         |       27.07       |