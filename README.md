# hybrid-skin-lesion-classification
Hybrid deep learning model for skin lesion classification combining Vision Transformer (ViT) and EfficientNet-B0 with selective hair-removal preprocessing on HAM10000 dataset.
# Google Colab Instructions for `final_hybrid_model_Skin_cancer_Multi_class_classification`

This notebook is designed to run on Google Colab and automate the dataset download process using the Kaggle API.

## 1. Prerequisites (One-Time Setup)

To automatically download the dataset as scripted in the notebook, you need to set up your Kaggle API token in your Google Drive.

1.  **Get Kaggle API Token:**
    *   Go to your [Kaggle Account Settings](https://www.kaggle.com/settings).
    *   Scroll down to the "API" section.
    *   Click **Create New Token**. This will download a file named `kaggle.json` to your computer.

2.  **Upload to Google Drive:**
    *   Go to your [Google Drive](https://drive.google.com/).
    *   Create the following folder structure exactly (or update the path in the notebook code):
        `My Drive` -> `Colab_Notebooks` -> `kaggle_API_TOKEN`
    *   Upload your `kaggle.json` file into this folder.
    *   **Final Path:** `/content/drive/MyDrive/Colab_Notebooks/kaggle_API_TOKEN/kaggle.json`

## 2. Running the Notebook

1.  **Open in Colab:**
    *   Upload the `final_hybrid_model_Skin_cancer_Multi_class_classification.ipynb` file to Google Colab.

2.  **Runtime Setup:**
    *   Go to **Runtime** > **Change runtime type**.
    *   Set **Hardware accelerator** to **GPU** (T4 GPU is standard).

3.  **Execute Cells:**
    *   **Run the first few cells.**
    *   When the cell with `drive.mount('/content/drive')` runs, it will ask for permission to access your Google Drive. Click **Connect to Google Drive** and approve.

4.  **Automatic Steps:**
    *   The notebook will automatically copy your `kaggle.json` from Drive to the correct system folder.
    *   It will download the **HAM10000** dataset from Kaggle.
    *   It will unzip the dataset into `/content/dataset`.
    *   It will install all necessary libraries (`torchmetrics`, `lightning-utilities`, etc.).

## 3. Troubleshooting

*   **File Not Found Error:** If you see an error about `kaggle.json` not found, verify you uploaded it to the exact folder path in Google Drive: `Colab_Notebooks/kaggle_API_TOKEN/`.
    *   *Alternative:* You can manually upload `kaggle.json` to the Colab runtime (files sidebar) and update the copy command in the code to `!cp kaggle.json ~/.kaggle/kaggle.json`.
*   **Dataset URL:** The notebook downloads from: [https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000).
