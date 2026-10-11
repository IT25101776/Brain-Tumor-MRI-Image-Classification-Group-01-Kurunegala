# Dataset

The MRI dataset is intentionally not committed to GitHub.

The notebooks download the final preprocessed dataset using KaggleHub:

```python
import kagglehub

path = kagglehub.dataset_download(
    "maleeshaweerakkody/brain-tumor-mri-preprocessed"
)
```

Keeping the dataset outside the repository avoids unnecessary repository size and duplication.
