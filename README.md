Automatic Number Plate Recognition using Streamlit
## Step 0: Environment Setup

Create a new environment with Python 3.9 and install TensorFlow 2.11.

```bash
# Create a new environment
conda create --name anpr-env python=3.9

# Activate the environment
conda activate anpr-env

# Install TensorFlow
pip install tensorflow==2.11
```

## Step 1: Download Kaggle Dataset

Download the dataset via Kaggle API or manually from Kaggle. Follow the instructions for downloading via Kaggle API.

1. **Install Kaggle API**:
    ```bash
    pip install kaggle
    ```

2. **Authenticate with Kaggle**:
    - Go to your [Kaggle Account](https://www.kaggle.com/account) and click on "Create New API Token". This will download a `kaggle.json` file.
    - Place the `kaggle.json` file in the location `~/.kaggle/` (on Windows: `C:\Users\<Your-Username>\.kaggle\`).

3. **Download the Dataset**:
    ```bash
    kaggle datasets download -d andrewmvd/car-plate-detection
    ```

## Step 2: Move Dataset into a Training and Testing Partition

Run the following script locally to prepare the dataset:

```bash
python ./1.PrepareDataset.py
```

## Step 3: Training and Detection

1. **Upload file `ANPR_and_EasyOCR_ColabRun_v1.ipynb` in Google Colaboratory**.

2. **Upload the prepared dataset archive** (created in Step 2) when running `ANPR_and_EasyOCR_ColabRun_v1.ipynb`. Place it in the directory `Tensorflow/workspace/images`.

3. **Note down the latest checkpoint** in the folder `Tensorflow/workspace/models/CUSTOM_MODEL_NAME/` (e.g., `ckpt-100`). This will be required to enter in the scripts `3.DetectFromImage_EasyOCR.py`, `4.DetectFromRealTimeFeed_EasyOCR.py`, `5.DetectFromVideos_EasyOCR.py`, and `app.py` where `LOAD_CHECKPOINT = 'ckpt-101'`.

4. After training, **download the compressed file of the trained model** into the project folder and uncompress it.

    **Note**: The scripts `3.DetectFromImage_EasyOCR.py`, `4.DetectFromRealTimeFeed_EasyOCR.py`, and `5.DetectFromVideos_EasyOCR.py` are optional.

## Step 4: Run the Streamlit UI

Add these instructions in your GitHub repository README file. For example:

```markdown
# ANPR and EasyOCR

## Step 0: Environment Setup

Create a new environment with Python 3.9 and install TensorFlow 2.11.

```bash
# Create a new environment
conda create --name anpr-env python=3.9

# Activate the environment
conda activate anpr-env

# Install TensorFlow
pip install tensorflow==2.11
```

## Step 1: Download Kaggle Dataset

Download the dataset via Kaggle API or manually from Kaggle. Follow the instructions for downloading via Kaggle API.

1. **Install Kaggle API**:
    ```bash
    pip install kaggle
    ```

2. **Authenticate with Kaggle**:
    - Go to your [Kaggle Account](https://www.kaggle.com/account) and click on "Create New API Token". This will download a `kaggle.json` file.
    - Place the `kaggle.json` file in the location `~/.kaggle/` (on Windows: `C:\Users\<Your-Username>\.kaggle\`).

3. **Download the Dataset**:
    ```bash
    kaggle datasets download -d andrewmvd/car-plate-detection
    ```

## Step 2: Move Dataset into a Training and Testing Partition

Run the following script locally to prepare the dataset:

```bash
python ./1.PrepareDataset.py
```

## Step 3: Training and Detection

1. **Upload file `ANPR_and_EasyOCR_ColabRun_v1.ipynb` in Google Colaboratory**.

2. **Upload the prepared dataset archive** (created in Step 2) when running `ANPR_and_EasyOCR_ColabRun_v1.ipynb`. Place it in the directory `Tensorflow/workspace/images`.

3. **Note down the latest checkpoint** in the folder `Tensorflow/workspace/models/CUSTOM_MODEL_NAME/` (e.g., `ckpt-100`). This will be required to enter in the scripts `3.DetectFromImage_EasyOCR.py`, `4.DetectFromRealTimeFeed_EasyOCR.py`, `5.DetectFromVideos_EasyOCR.py`, and `app.py` where `LOAD_CHECKPOINT = 'ckpt-101'`.

4. After training, **download the compressed file of the trained model** into the project folder and uncompress it.

    **Note**: The scripts `3.DetectFromImage_EasyOCR.py`, `4.DetectFromRealTimeFeed_EasyOCR.py`, and `5.DetectFromVideos_EasyOCR.py` are optional.

## Step 4: Run the Streamlit UI(streamlit run app.py)

This guide provides a clear and structured way to set up, download, train, and run the ANPR project using TensorFlow and EasyOCR.
