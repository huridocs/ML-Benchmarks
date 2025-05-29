Dataset: upr_action (5 labels, single label classification)

| Model                                  | Train/Test Samples | Train Rounds          | Average Train Accuracy | Test Set Accuracy |
|----------------------------------------|--------------------|-----------------------|------------------------|-------------------|
| claude sonnet 3.7                      | 19801/79203        | 10                    | 51                     | 67.74             |
| chatgpt-4.1                            | 19801/79203        | 7 (stopped manually)  | 39.08                  | 49.74             |
| deepseek-v3                            | 19801/79203        | 5                     | 31.59                  | 40.98             |          

I stopped ChatGPT earlier because it started creating lots of repetitions, not ending the output.



Dataset: plan_persons_affected (17 labels, multi label classification)
| Model                                  | Train/Test Samples | Train Rounds          | Average Train Accuracy | Test Set Accuracy |
|----------------------------------------|--------------------|------------------------|-----------------------|-------------------|
| claude sonnet 3.7                      | 59015/236058       | 3                      | 27.74                 | 60.74             |
| deepseek-v3                            | 59015/236058       | 3                      | 13.03                 | 22                |   
| chatgpt-4.1                            | 59015/236058       | 3                      | 18.27                 | 20.14             |

I stopped training after 3 rounds because ChatGPT started creating repetitions and Sonnet was decreasing after every round.



Dataset: plan_topics (16 labels, multi label classification)
| Model                                  | Train/Test Samples | Train Rounds          | Average Train Accuracy | Test Set Accuracy |
|----------------------------------------|--------------------|------------------------|-----------------------|-------------------|
| chatgpt-4.1                            | 43281/173124       | 2 (stopped manually)   | 31.69                 | 31.26             |
| claude sonnet 3.7                      | 43281/173124       | 3                      | 21.23                 | 25.97             |
| deepseek-v3                            | 43281/173124       | 1 (stopped manually)   | 19.72                 | 19.45             |   

Stopped ChatGPT and Deepseek earlier because they started creating lots of repetitions and not ending the output.



Dataset: upr_issues (69 labels, multi label classification)
| Model                                  | Train/Test Samples | Train Rounds          | Average Train Accuracy       | Test Set Accuracy |
|----------------------------------------|--------------------|-----------------------|------------------------------|-------------------|
| chatgpt-4.1                            | 19762/79046        | 3                     | 32.55                        | 36.55             |
| deepseek-v3                            | 19762/79046        | 3                     | 22.59                        | 29                |   
| claude sonnet 3.7                      | 19762/79046        | -                     | (output token limit reached) | -                 |

I stopped this one very early because models started creating lots of repetitions and not ending the output.






Dataset: plan_persons_affected (17 labels, multi label classification)
| Model                                  | Train/Test Samples | Mistakes Fed to Prompt | Average Test Accuracy        | Average Test Accuracy After Feeding the Mistakes in Prompt|
|----------------------------------------|--------------------|------------------------|------------------------------|-----------------------------------------------------------|
| claude sonnet 3.7 (no code)            | 17/17              | 5                      | 89.85                        | 99.16                                                     |
| deepseek-v3 (no code)                  | 17/17              | 7                      | 78.43                        | 98.04                                                     |   
| chatgpt-4.1 (no code)                  | 17/17              | 7                      | 72.06                        | 100                                                       |



Dataset: plan_topics (16 labels, multi label classification)
| Model                                  | Train/Test Samples | Mistakes Fed to Prompt | Average Test Accuracy        | Average Test Accuracy After Feeding the Mistakes in Prompt|
|----------------------------------------|--------------------|------------------------|------------------------------|-----------------------------------------------------------|
| deepseek-v3 (no code)                  | 16/21              | 8                      | 82.94                        | 100                                                       |   
| chatgpt-4.1 (no code)                  | 16/21              | 10                     | 79.37                        | 100                                                       |
| claude sonnet 3.7 (no code)            | 16/21              | 12                     | 77.22                        | 97.14                                                     |



Dataset: upr_issues (69 labels, multi label classification)
| Model                                  | Train/Test Samples | Mistakes Fed to Prompt | Average Test Accuracy        | Average Test Accuracy After Feeding the Mistakes in Prompt|
|----------------------------------------|--------------------|------------------------|------------------------------|-----------------------------------------------------------|
| deepseek-v3 (no code)                  | 69/21              | 14                     | 64.33                        | 97.62                                                     |   
| chatgpt-4.1 (no code)                  | 69/21              | 15                     | 62.59                        | 100                                                       |

I was not able to try claude sonnet 3.7 since I got out of tokens