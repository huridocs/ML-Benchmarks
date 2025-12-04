```
| model              | not_found_labels | wrong_segmentation | wrong_token_type | mistakes | accuracy |
|--------------------|------------------|--------------------|------------------|----------|----------|
| vgt                | 137              | 5                  | 119              | 261      | 95.44    |
| marker             | 191              | 17                 | 179              | 387      | 93.23    |
| marker_llama3.1    | 194              | 16                 | 181              | 391      | 93.16    |
| marker_phi4        | 196              | 17                 | 184              | 397      | 92.92    |
| marker_aya-expanse | 198              | 17                 | 186              | 401      | 92.99    |
| mineru             | 252              | 9                  | 173              | 434      | 92.41    |
| docling            | 249              | 35                 | 211              | 495      | 91.36    |
| yolov8x            | 253              | 27                 | 286              | 566      | 90.24    |
| yolov10b           | 290              | 32                 | 249              | 571      | 90.17    |
| aryn-ai            | 332              | 13                 | 234              | 579      | 89.88    |
| yolov10m           | 268              | 34                 | 290              | 592      | 89.85    |
| lightgbm           | 413              | 50                 | 416              | 879      | 84.67    |
| deepdoc            | 660              | 189                | 308              | 1157     | 81.24    |
```

- For dataset, I have used [benchmark_segmentation](https://github.com/huridocs/pdf-labeled-data/tree/main/labeled_data/benchmark_segmentation) dataset in [pdf_labeled_data](https://github.com/huridocs/pdf-labeled-data) repo.
- VGT still seems like the better model when it comes to segmentation.
- Using marker with LLMs didn't help, at least for local - smaller models.
- I have also tried using smoldocling, which is a model works on images rather than the documents themselves, but it uses around ~12.5 GB of GPU memory, is slower, and gives worse results.


- Yolo models are from:
    - https://huggingface.co/Oblix/yolov10m-doclaynet_ONNX_document-layout-analysis
    - https://huggingface.co/Oblix/yolov10b-doclaynet_ONNX_document-layout-analysis
    - https://huggingface.co/Oblix/yolov8x-doclaynet_ONNX