
---

# Information Retrieval System (IR System)

This program implements an **Information Retrieval System** that allows searching documents from a directory using different search models. The user can choose between three different search models to perform the queries:

1. **Boolean Model**
2. **Exact Match Search**
3. **Vector Space Model with TF-IDF**

The program also allows evaluating the system's performance by calculating **precision** and **recall** based on the relevant documents provided by the user.

## Prerequisites

- **Python 3.x**  
- The following libraries need to be installed:
  - `scikit-learn`
  - `numpy`

You can install the required libraries using `pip`:
```bash
pip install scikit-learn numpy
```

## Features

### 1. Boolean Model
Allows searching for documents containing specific terms using **AND**, **OR**, and **NOT** Boolean operators.

### 2. Exact Match Search
Performs a search that returns documents containing the exact string entered by the user.

### 3. Vector Space Model
Uses **TF-IDF** (Term Frequency-Inverse Document Frequency) and **cosine similarity** to find the documents most similar to the query. The user can specify how many results to return.

### Precision and Recall Evaluation
After each search, the user can input the relevant documents. The system then calculates **precision** and **recall** for the search results based on the relevant documents provided.

## How It Works

### Document Loading
Documents are loaded from a specific directory. Files should be stored in a directory and must be text files (`.txt`).

### Search Workflow
1. The user chooses the search model (Boolean model, Exact match, or Vector space).
2. The user enters a **search query**.
3. If the Vector Space Model is chosen, the user can specify the number of results to display.
4. The program performs the search and displays the results with associated numbers for easier reference.
5. The user can input the numbers of the relevant documents.
6. The system calculates **precision** and **recall** for the search results.

### Example Usage

1. **Choose a model**:  
   When you run the program, it will prompt you to choose a model from the following options:
   ```text
   1: Boolean Model
   2: Exact Match Search
   3: Vector Space Model
   ```

2. **Enter a query**:  
   After selecting the model, you will need to enter a search query.

3. **Enter relevant documents**:  
   After the results are displayed, you can enter the numbers of the relevant documents. The program will then return precision and recall metrics for the results.

### Example of Selecting Relevant Documents

```text
Enter relevant document numbers separated by commas (if known): 1, 3, 5
```

This allows the system to compute the **precision** and **recall** to evaluate the quality of the returned results.

### Performance Measurement

The program measures and displays the execution time and memory usage for each search. It also calculates **precision** and **recall** based on the relevant documents provided by the user.

## Main Code

```python
import os
import time
from collections import defaultdict
import re
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import cosine_similarity
import tracemalloc

class InformationRetrievalSystem:
    # Class implementation...
    # See full code above
```

## File Structure

The program assumes that the documents are stored in a specific directory. The name of the directory is provided when creating the instance of the retrieval system.

For example, if you have a folder called `recipes/` containing text files with recipes, you need to provide this path to the program when initializing it:
```python
ir_system = InformationRetrievalSystem("recipes")
```

## Contributing

If you would like to contribute to this project, feel free to open an **issue** or submit a **pull request**.

---

### Additional Notes:

- The system is designed to be flexible and could be extended to incorporate more advanced search features, such as term weighting or the use of different similarity algorithms.
  
- You can also customize the evaluation methods to include additional metrics like **F-measure** or other metrics depending on your needs.

---
