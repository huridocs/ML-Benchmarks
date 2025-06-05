|               Method              | Train/Test Samples | Train Rounds | Average Train Accuracy | Test Set Accuracy |
|-----------------------------------|--------------------|--------------|------------------------|-------------------|
|        contrastive_learning       |     19801/79203    |       6      |          53.28         |       70.25       |
|        constraints_no_regex       |     19801/79203    |       7      |          53.09         |       70.14       |
|       multi_stage_filtering       |     19801/79203    |       6      |          50.95         |       68.85       |
|   constraints_dictionary_mapping  |     19801/79203    |       5      |          41.94         |       68.32       |
|           default prompt          |     19801/79203    |      10      |          51.0          |       67.74       |
|   special_instructions_linguist   |     19801/79203    |       7      |          50.17         |       65.66       |
|  special_instructions_robustness  |     19801/79203    |       4      |          49.73         |        65.1       |
|  special_instructions_simplicity  |     19801/79203    |       4      |          39.09         |       61.67       |
|           scoring_system          |     19801/79203    |       4      |          46.85         |       53.59       |
|special_instructions_data_scientist|     19801/79203    |       3      |          43.45         |       51.42       |
|          self_reflection          |     19801/79203    |       3      |          40.02         |       50.84       |
|        reverse_engineering        |     19801/79203    |       4      |          40.98         |       49.53       |
|       constraints_only_elif       |     19801/79203    |       8      |          41.36         |        49.5       |
|  constraints_only_substring_match |     19801/79203    |       3      |          33.54         |       42.95       |
|        constraints_no_loops       |     19801/79203    |       5      |          36.44         |        42.9       |
|          chain_of_thought         |     19801/79203    |       2      |          31.8          |       38.47       |
|             same_chat             |     19801/79203    |       3      |          26.38         |       27.07       |