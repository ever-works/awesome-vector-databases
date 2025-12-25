# Machine Learning Crash Course: Embeddings

**Brand:** Google Developers  
**Category:** Concepts & Definitions  
**URL:** https://developers.google.com/machine-learning/crash-course/embeddings

## Overview
Module in Google’s Machine Learning Crash Course that introduces embeddings—dense, lower-dimensional representations of sparse data. It explains why embeddings are needed, how they are constructed, and how they capture semantic relationships, providing essential background for using vector representations in machine learning, vector databases, and similarity search.

## Key Topics Covered
- Motivation for embeddings in practical ML applications (e.g., recommendation systems)
- Limitations of one-hot encoding and other sparse representations
- Concept of dense, low-dimensional vector representations
- How embeddings capture semantic similarity between items
- Relationship between embeddings and neural network architectures
- Background needed: linear regression, categorical data, neural networks

## Features
- **Problem Setup Example**
  - Uses a food-recommendation application as a running example (predicting similarity between meals).
  - Demonstrates how user preferences (e.g., liking pancakes) can be used to suggest similar items (e.g., crepes).
  - Works with a curated dataset of 5,000 meal items (e.g., borscht, hot dog, salad, pizza, shawarma).

- **Encoding Categorical Data**
  - Introduces the `meal` feature as a categorical variable.
  - Explains **one-hot encoding** as an initial numerical representation.
  - Clarifies that “encoding” is the general process of turning raw data into numeric inputs for models.

- **Pitfalls of Sparse Representations (One-Hot Encodings)**
  - **Number of weights**
    - With M categories and N nodes in the first hidden layer, a neural network must learn M×N weights.
    - Large input vectors directly inflate model parameter count.
  - **Number of datapoints needed**
    - More weights require more training data to learn effectively and avoid overfitting.
  - **Computation cost**
    - Increased weights raise training and inference time.
    - Potential to exceed realistic hardware capabilities.
  - **Memory usage**
    - High parameter counts demand more memory on training and serving accelerators.
    - Scaling such models becomes challenging.
  - **On-device ML constraints**
    - Large models are difficult to deploy on devices with limited compute and memory.
    - Highlights the importance of reducing model size and number of weights for ODML.

- **Lack of Semantic Relationships in One-Hot Vectors**
  - One-hot encoded vectors do not capture similarity between categories.
  - Example: hot dog and shawarma are intuitively more similar to each other than hot dog and salad, but one-hot encoding treats all pairwise distances as equivalent.
  - Emphasizes the need for representations where distance reflects semantic closeness.

- **Introduction to Embeddings**
  - Defines **embeddings** as lower-dimensional, dense vectors representing items (e.g., words, meals, other categorical entities).
  - Explains that embeddings:
    - Reduce dimensionality compared to one-hot encodings.
    - Capture semantic relationships (similar items have similar vectors).
    - Improve modeling efficiency and performance.
  - Positions embeddings as a core technique for modern ML tasks, including similarity search and recommendation.

- **Assumed Background Knowledge**
  - Basic understanding of:
    - Linear regression
    - Categorical variables and their encodings
    - Neural networks and weights

## Use Cases Highlighted
- Building recommendation systems (e.g., food recommendation).
- Any ML setup requiring similarity measures between discrete items.
- Foundational understanding for vector databases and similarity search systems.

## Format & Access
- Part of Google’s **Machine Learning Crash Course – ML Concepts** track.
- Web-based, self-paced module.
- Available in multiple languages via the Google Developers platform.

## Pricing
- Not specified in the provided content. (Google’s ML Crash Course modules are generally available free of charge.)