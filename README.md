pbanjara

# Risk Language Detection on Reddit Mental Health Posts
This part of the project involves data sampling, data labeling, training and evaluating baseline (TF-IDF and Logistic Regression) and transformer-based models (RoBERTa, DistilBERT, and SBERT), and integrating topic and risks.

## Data Source
Primary corpus comes from a publicly available dataset on [Hugging Face](https://huggingface.co/datasets/solomonk/reddit_mental_health_posts), which contains approximately 151,000 Reddit posts from five mental health subreddits: depression, PTSD, OCD, ADHD, and Aspergers. 

## Project Structure
```
├── materials/                                          Data files for model training and evaluation
│   ├── final_sets/                                     Labeled Sets
│   ├── test_labeled_set.csv
│   ├── train_labeled_set.csv
│   ├── val_labeled_set.csv
│   │      
│   ├── models_integration/                             Data files for topic and risk integration
│   │   ├── figure_data_topic_prevalence_over_time.csv
│   │   ├── integration_with_risk_predictions.csv
│   │   ├── integration_data.csv
│   ├── saved_images/ 
├── gitignore
├── exploring_and_sampling.ipynb                          Exploratory Analysis and Sampling
├── labeling.ipynb                                        Data labeling using OpenAI API 
├── model_training.ipynb                                  Model training pipelines
├── README.md
└── topics_risks_integration.ipynb                        Integration pipeline
```

## Running code

1. Download the data from this repository by either using git clone `https://github.com/Social-Media-Help-Seeking-ML/pbanjara.git` for HTTPS or using git clone `git@github.com:Social-Media-Help-Seeking-ML/pbanjara.git` for SSH. It can also be downloaded manually by clicking on <strong>Code</strong> >> <strong>Download Zip</strong>.

2. Create a virtual environment and activate it. 

3. Install necessary packages listed on the requirements.txt into the virtual environment.

4. Run exploring_and_sampling.ipynb file for data exploration and sampling.

5. Run labeling.ipynb file for sending sampled posts and prompts as a single string to OpenAI API, which returns a string with a label for a post along with a reasoning. The labels and reasonings are then extracted from the single string and added to the dataframe. Note: This requires an OpenAI API key, which can be stored in a .env file. Also, the API key needs separate payment.

6. Run model_training.ipynb to run all the models and generate results and visualizations.

7. Run topic_risks_integration.ipynb to run the integration pipeline and generating a heat map with topic keywords and predicted risk labels.
