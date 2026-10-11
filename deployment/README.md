# Deployment

After the group selects the final deployable model:

1. Run the selected model notebook completely.
2. Download the saved model and its metadata.
3. Keep the exact class order and preprocessing used during training.
4. Build the Streamlit app around that exact model.

Large model binaries such as `.keras` files are excluded from normal Git by `.gitignore`.

For GitHub, store a large final model using one of these options:

- Git LFS
- GitHub Releases
- External cloud storage approved by the group/lecturer

Do not use a different preprocessing pipeline in the app from the one used during training.
