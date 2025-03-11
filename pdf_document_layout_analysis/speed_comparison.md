| Model    | GPU | Hardware          | Speed (s/page) |
|----------|:---:|:------------------|---------------:|
| LightGBM |  ✗  | Intel i7-14700K   |           0.04 |
| LightGBM |  ✗  | Intel i7-8700     |           0.42 |
| deepdoc  |  ✗  | Intel i7-14700K   |           0.34 |
| VGT      |  ✓  | RTX 4070 TI Super |           0.34 |
| VGT      |  ✓  | GTX 1070          |           1.75 |
| VGT      |  ✗  | Intel i7-14700K   |           7.45 |
| VGT      |  ✗  | Intel i7-8700     |           13.5 |
| docling  |  ✓  | RTX 4070 TI Super |           0.39 |
| docling  |  ✓  | GTX 1070          |           0.89 |
| docling  |  ✗  | Intel i7-14700K   |           0.61 |
| marker   |  ✓  | RTX 4070 TI Super |           0.44 |
| marker   |  ✓  | GTX 1070          |           1.09 |
| marker   |  ✗  | Intel i7-14700K   |           1.04 |

---

| Model    |  GPU Memory  |
|----------|:------------:|
| LightGBM |      ✗       |
| deepdoc  |      ✗       |
| VGT      |   ~4.2 GB    |
| marker   |   ~3.2 GB    |
| docling  |   ~1.7 GB    |

