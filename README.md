### 1. Dependencies
Run to install stuff required to run the code:
```bash
pip install -r dependencies.txt

What I did to install torch (pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118)

### 2. Dataset
The dataset is available on Kaggle (https://www.kaggle.com/datasets/najzeko/steam-reviews-2021 8 GB). This dataset was cleaned and reduced down to 316 games using clean_dataset.ipynb. After it was cleaned I used Gemini to generate the outputs and put them into the csv file. Final file: processed_reviews_2.csv.

### 3. LoRA_tuning_7B.ipynb
Run the code blocks in order:
1. First block loads the dataset.
2. Second block downloads and loads the base model (Mistral 7B). It also splits the data into testing and training (10/90).
3. Loads the same dataset with different formating for evaluating the base model
4. Evaluates the base model using rouge scores.
5. Imports LoRA, adds trainable parameters and configuration.
6. Loads the Hugging Face Trainer and configures it.
7. Trains the model using the processed dataset.
8. Saves the model.
9. Reloads the model. If previous code was already successful in running you don't need to run this. If you want to save time and just load the trained model run this block.
10. Loads the same evaluation dataset.
11. Evaluates the trained model.


