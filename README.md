# Movie Script Analysis Project

## Data Source
This project utilizes two public datasets from Kaggle:
1. **Movie Scripts Dataset**: A collection of movie scripts, each stored in a separate file within a folder.
2. **IMDb Data**: A CSV file containing movie details such as name, ID, rating, genre, etc., scraped from the IMDb website.

## Merging the Data
To create a unified dataset:
- We merged the datasets using the `IMDb ID`.
- Script files were named `<name>_Movieid.txt`. We generated filenames from the movie name and ID in the CSV and matched these to the script filenames.
- Adjustments were made to handle discrepancies in movie names, such as removed punctuation.

## Data Cleaning
- Removed rows without a rating or script.
- Eliminated newline (`\n`) and tab (`\t`) characters from scripts.
- Excluded genres heavily reliant on visuals (action, sci-fi, horror) from the analysis.

## Model Selection
We chose the **BigBird Transformer model**, an extension of BERT, designed for long sequences (up to 4,096 tokens). This model is ideal for handling the extensive content of movie scripts with its sparse attention mechanism, allowing efficient processing of longer documents.

## Training and Testing
- Divided the dataset into training, validation, and testing subsets.
- Used the validation dataset for hyperparameter tuning and to prevent overfitting.
- Performed a grid search to optimize hyperparameter selection.
- Evaluated the model on the test dataset after training.

## Outcomes
- **Accuracy**: 66%
- **Precision**: 0.59
- **Recall**: 0.50
- **F1 Score**: 0.54

## Model Improvement Plans
- **More Data**: Acquiring additional data to improve model training and accuracy.
- **Additional Features**: Exploring other predictive elements that could enhance the accuracy of rating predictions.
- **Increased Computing Power**: Upgrading our hardware to support longer training periods and improve model performance.

## Bias Considerations
Potential biases include:
- **Selection Bias**: Non-representative script dataset.
- **Label Bias**: Subjectivity in IMDb ratings.
- **Textual Bias**: Bias towards certain themes or styles prevalent in scripts.
- **Confirmation Bias**: Reinforcement of stereotypes or popular opinions.

## Risks and Unintended Consequences
- **Innovation Stifling**: Favoring historically successful scripts may discourage innovative storytelling.
- **Economic Impact**: Predictive models might skew funding towards scripts predicted to be successful, neglecting experimental works.
- **Self-fulfilling Prophecy**: Model predictions could influence public and critical perception, impacting actual movie ratings.
