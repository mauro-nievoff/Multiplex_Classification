# Multiplex Classification
The Multiplex Classification Framework is a novel approach designed to address complex machine learning classification problems by integrating problem transformation, ontology engineering, and model ensembling.

In this repository you will find:
- Code: Scripts used to adapt taxonomies and CSV files.
- Sample OWL files: including input and ouput OWL format.
- Experimental Files: Datasets, notebooks, and OWL files from the HyperKvasir and the MultiCaRe experiments.

## How to use
1. Clone the repository:
```python
!git clone https://github.com/mauro-nievoff/Multiplex_Classification
!pip install -r Multiplex_Classification/requirements.txt
```

2. Import the relevant classes
```python
from Multiplex_Classification.multiplex import MultiplexTaxonomyProcessor, MultiplexDatasetProcessor
```

3. Adapt your dataset based on your taxonomy:
```python
mdp = MultiplexDatasetProcessor(input_owl_path = 'path_to_your_taxonomy.owl', input_csv_path = 'path_to_your_dataset.csv')
```
