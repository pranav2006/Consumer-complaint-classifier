
# Customer Complaint Classification Model

This project implements a text classification model using spaCy to classify customer complaints into two categories: **High** and **Low** priority. The model is trained using complaint data and can be used to automatically categorize new complaints based on their content.

## Use Case: Prioritizing Jira Tickets
This model can be applied to prioritize Jira tickets or other customer service tickets in companies. Many organizations rely on ticketing systems like Jira to manage tasks and complaints. However, not all tickets are created equal. Some require immediate attention (High priority), while others can be addressed later (Low priority).

## Requirements

To get started, clone this repository and install the required dependencies.

### Install Dependencies

To install the necessary dependencies, create a virtual environment and install the packages listed in the `requirements.txt` file:

```bash
# Create a virtual environment (optional)
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install the required libraries
pip install -r requirements.txt
```

### Dependencies

- `spaCy`: NLP library for text classification and processing.
- `pandas`: Library for data manipulation and analysis.
- `random`: Python module used to shuffle the dataset during training.
- `spacy-training`: Module for creating training examples using spaCy's `Example` class.

## Dataset

The dataset `Customer Complaints Sentiment and Priority Dataset.csv` contains customer complaints and their corresponding priority labels. The priority can either be **High** or **Low**.



## Using the Model

You can use it to predict the priority of new customer complaints.

### Example Usage

```python
import spacy

# Load the trained model
nlp = spacy.load("complaint_classifier")

# Test the model
test_text = "The product was broken when it arrived"
doc = nlp(test_text)

# Print the prediction
print(test_text)
print(doc.cats)  # Shows the probability of each category: High, Low
```

### Output Example

```python
"The product was broken when it arrived"
{'High': 0.85, 'Low': 0.15}
```

This shows that the model predicts the complaint as **High priority** with 85% confidence.

## Model Evaluation

You can evaluate the model's performance by testing it on a separate test set (not provided in this repository) or by manually checking its predictions on various complaints.

## Future Improvements

- **Additional Labels**: You can extend the model to classify complaints into more categories, such as **Medium** priority.
- **Pretrained Models**: Integrating pretrained models such as BERT or RoBERTa for better accuracy on larger datasets.
- **Deployment**: Deploying the model as a web service using FastAPI or Flask for real-time predictions.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
