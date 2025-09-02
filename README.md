GDG Project
🔄 Reusability of Code

This repository is structured to make both preprocessing and modeling highly reusable across different datasets and experiments.

⚙️ Running Locally

Clone the repository:

git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>


Install dependencies:

pip install -r requirements.txt

🧹 Preprocessing

We provide reusable functions for preparing data:

For classical ML models

preprocess_data(X_train, X_test, text_col, y_train, y_test)


This function automatically:

Scales numerical columns

One-hot encodes categorical columns

Applies TF-IDF on text columns

For deep learning models

preprocess_data(df, categorical_cols, numeric_cols, text_col, max_words=10000, max_len=100, test_size=0.2):

just give the names of cols as a list
This includes tokenization and generates inputs that can be fed directly into deep learning architectures (e.g., BiLSTMs, Transformers).

🤖 Modeling

The workflow for training and evaluation is built around the evaluate_model function:

Swap in any model (e.g., RandomForest, XGBoost, Logistic Regression, BiLSTM).

Call:

evaluate_model(model, X_train, X_test, y_train, y_test)


to:

Train the model

Compute key metrics (accuracy, precision, recall, F1, etc.)

Return results in a standardized format

This modular structure allows you to:

Compare ML and DL models directly

Reuse preprocessing and evaluation code without duplication

Extend the pipeline with minimal effort

