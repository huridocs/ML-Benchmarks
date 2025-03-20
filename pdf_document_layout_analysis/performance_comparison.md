```
| model              | not_found_labels | wrong_segmentation | wrong_token_type | mistakes | accuracy |
|--------------------|------------------|--------------------|------------------|----------|----------|
| deepdoc            | 660              | 189                | 308              | 1157     | 81.24    |
| docling            | 249              | 35                 | 211              | 495      | 91.36    |
| lightgbm           | 413              | 50                 | 416              | 879      | 84.67    |
| marker             | 191              | 17                 | 179              | 387      | 93.23    |
| marker_aya-expanse | 198              | 17                 | 186              | 401      | 92.99    |
| marker_llama3.1    | 194              | 16                 | 181              | 391      | 93.16    |
| marker_phi4        | 196              | 17                 | 184              | 397      | 92.92    |
| vgt                | 137              | 5                  | 119              | 261      | 95.44    |
```

- For dataset, I have used [benchmark_segmentation](https://github.com/huridocs/pdf-labeled-data/tree/main/labeled_data/benchmark_segmentation) dataset in [pdf_labeled_data](https://github.com/huridocs/pdf-labeled-data) repo.
- VGT still seems like the better model when it comes to segmentation.
- Using marker with LLMs didn't help, at least for local - smaller models.
- I have also tried using smoldocling, which is a model works on images rather than the documents themselves, but it uses around ~12.5 GB of GPU memory, is slower, and gives worse results.
