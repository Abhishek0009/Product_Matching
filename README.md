# Product Matching using CLIP and Sentence Transformers

This project demonstrates a product matching engine built using CLIP for image and text embeddings and Sentence Transformers for similarity search. It indexes a dataset of product descriptions and images, allowing for searches based on both text queries and image uploads.

## Functionality

1. **Data Loading and Preprocessing:** Reads product data from a CSV file (`flipkart_com-ecommerce_sample.csv`).

2. **Embedding Generation:** 
    - Uses the CLIP model to generate embeddings for both product descriptions and images.
    - Divides long text descriptions into chunks for better representation.
    - Handles image URLs, downloading and processing them for embedding.

3. **Vector Database (In-Memory):** Creates an in-memory index mapping product IDs to their corresponding embedding ranges within a combined embedding tensor.

4. **Querying:** Offers two search methods:
    - `search(query)`: Searches based on a text query.
    - `search_image(image_path)`: Searches based on an uploaded image.
    - Both methods use Sentence Transformer's cosine similarity to rank results and return top matches with their associated image links.

5. **Pickling:** Pickles embedding, index map, and dataframe for further usage.

## Requirements

- pandas
- Pillow (PIL)
- torch
- transformers
- requests
- sentence-transformers

Install required libraries:
```sh
pip install pandas pillow torch transformers requests sentence-transformers
```
## REFERENCES
[https://www.semanticscholar.org/paper/E-Commerce-Product-Matching-at-Internet-Scale-Sortur-Rajpoot/4bf61ee288cdc4d62dcec6289d80d3b7c6571744](https://www.semanticscholar.org/paper/E-Commerce-Product-Matching-at-Internet-Scale-Sortur-Rajpoot/4bf61ee288cdc4d62dcec6289d80d3b7c6571744)

[text](https://arxiv.org/html/2409.11860v1)

[text](https://colab.research.google.com/drive/1UrS-_MuxWtvjQGgVCIMydR_iF51SOgli#scrollTo=M1joSIhfULe0&uniqifier=1)

[Flipkart_data](https://www.kaggle.com/datasets/PromptCloudHQ/flipkart-products)